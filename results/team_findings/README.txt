ENGG2112 — TEAM FINDINGS

START HERE
Open OPEN_ME_results.html in a web browser.
The CSV files contain the same results for Excel or report tables.

PROJECT QUESTION
Can models trained on several lakes predict bloom conditions during
an upcoming ten-day period at an unseen lake, and does including
Erie imagery during training improve this transfer?

DATA
539 forecasting examples across four lakes:
- Erie: 221
- Okeechobee: 176
- Champlain: 71
- Upper Klamath: 71

Each example pairs an upcoming ten-day bloom label with environmental
information from the preceding ten days.

The five environmental inputs are:
- Rainfall total
- Mean river discharge
- Water-level change
- Seasonal sine
- Seasonal cosine

EVALUATION
One entire lake was held out for testing in each experiment.
For the remaining lakes, the latest available year was reserved for
validation and earlier years were used for training.

VALIDATION versus TEST
Validation selected training checkpoints.
Test results measured performance on the excluded lake.
A validation row named "Okeechobee" therefore refers to validation
on the OTHER lakes in the Okeechobee-held-out experiment.

MODELS
Environmental MLP: environmental inputs only.
MLP + CNN: environmental inputs plus image features when available.
Training-majority baseline: always predicts the most common training class.
Season-only MLP: uses only the seasonal inputs.
Availability-only control: removes image features while retaining
the image-availability indicator and combined architecture.

IMAGE LIMITATION
Only Erie had satellite images.
The combined model was evaluated on the other three lakes without
images at prediction time. No combined model was trained in the
Erie-held-out fold because that fold had no training imagery.

MAIN FINDINGS FROM THE ORIGINAL RUN
Across Champlain, Okeechobee and Upper Klamath:
- Environmental MLP average F1: 0.572
- Combined MLP + CNN average F1: 0.707
These are equal-weight averages across the three lakes.

Transfer performance varied substantially between lakes.
The season-only model outperformed the combined model on Champlain.
The signed-log flow experiment did not consistently improve transfer.

INTERPRETATION
These results concern experimental bloom-condition labels, not toxin
concentrations or confirmed water safety.

Source labels and observation coverage were imperfect, and some
supplied environmental records were reconstructed. Performance is
therefore agreement with the prepared dataset, not independently
verified operational forecasting accuracy.

Follow-up experiments were conducted after inspecting test results.
They should be described as exploratory. Results are from a single
random seed and do not establish that imagery always improves transfer.

FILES
Only tables available in the current notebook session were exported.
A missing table does not mean that its experiment was never completed.
The signed-log results remain in results/cross_lake_v2/signed_log_flow
if they were saved there by the earlier experiment.
