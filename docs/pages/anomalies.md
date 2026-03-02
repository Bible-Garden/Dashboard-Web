# Product Specification: Anomalies Page

This is the only page that needs to be tested.

## Overview
The **Bible Anomalies** page is designed for detecting, reviewing, and correcting errors (anomalies) in word-level audio alignment of Bible recordings. Anomalies occur when timestamps for words in the audio file do not match the actual pronunciation or are missing.

## Main Features

### 1. Filtering and Selection
Users can filter the anomaly list by the following criteria:
- **Voice**: Required selection. Shows statistics of open and total anomalies for each voice.
- **Book**: Filter by a specific Bible book.
- **Anomaly Type**: Filter by problem type (e.g., `missing_word`, `alignment_error`).
- **Status**: Filter by processing status (e.g., `detected`, `confirmed`, `fixed`).

### 2. Anomaly List (Table)
Displays a list of detected issues with the following columns:
- **Code**: Unique anomaly code.
- **Reference**: Verse reference (Book Chapter:Verse).
- **Word**: Problematic word (or count of anomalies in the verse).
- **Anomaly Type**: Tags indicating the type of problem.
- **Info**: Additional information/hints.
- **Ratio**: Deviation coefficient (how much timings differ from expected).
- **Status**: Current status. Allows quick status changes via dropdown menu.
- **Actions**: Play button for listening to the context.

### 3. Audio Player and Navigation
A floating mini-player is available for detailed review:
- **Playback**: Play the current verse with word highlighting.
- **Navigation**: Navigate to next/previous verse.
- **Quick Check**: Fast listening mode (beginning and end of verse) for quicker review.
- **Auto Advance**: Automatic navigation to the next anomaly after actions.

### 4. Timing Correction (Verse Correction)
Tool for manual correction of verse timestamps:
- **Adjust Start/End Time**: Buttons to shift verse start and end with different steps (1.0s, 0.1s, 0.01s).
- **Preview**: Listen to the corrected fragment.
- **Overlap Detection**: Automatic detection of overlaps with neighboring verses (Begin/End Overlap) and tools to fix them.

### 5. Creating Anomalies
Ability to manually create an anomaly ticket via a dialog, if an error is found by the user but not detected automatically by the system.

## Workflow
1. Operator selects a **Voice**.
2. System loads the list of detected anomalies.
3. Operator listens to the verse by clicking **Play**.
4. If the error is confirmed, operator clicks **Confirm Error**.
5. If alignment is correct, operator clicks **Alignment Correct**.
6. If timing correction is needed, operator opens **Adjust Verse Timing**, adjusts boundaries, and applies changes (**Apply Corrections**).
7. If **Auto Advance** mode is enabled, the system automatically navigates to the next problematic spot.
