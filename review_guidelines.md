---
layout: page
title: Review Guidelines
permalink: /guidelines/
---

## ACM ICMR Reproducibility Review Guidelines

Please also refer to the [ACM ICMR Reproducibility pages](./cfp2024/) for information about what an ideal repro submission should have. 
When addressing the work, make sure that you write in a way that you yourself would like to see in a review that you get. 

A reproducibility review is different from a standard conference review. In particular: 

- Interacting with the authors is the most important thing. As soon as you are blocked, if anything fails during the installation, the execution, if any result appears to be strange, then in parallel to trying to figure out what is going on, please talk to the authors. You will lose less time. Maybe the overall duration of the review process will increase, but this does not matter.
- The assumption is that (a) the original ACM ICMR paper contains valid science and (b) that the corresponding repro paper indeed supports the findings and can be trusted. The goal of all this repro track is to work such that repro paper *eventually* gets accepted once what they propose is clear and clean enough for other members of the community to build on their findings. It may take time, it may take many iterations and discussions with the authors, but the goal is to have them pass the reviewing phase after updates and adjustments. Rejects should really be limited to the cases where something goes wrong: it requires tremendous work to reproduce the findings; where there is something that is very unclear or incorrect; or where authors do not discuss with you in an open and friendly way, as if they were trying to hide something from your sight.
- Take special care if the system you receive is a black box. We must try to make as much as possible sure that the binaries received are indeed truly running what is described in the ACM ICMR paper. We must make sure that authors have not created some piece of software that ingests a few parameters that users can vary and then their code simply prints out the results that are expected, without running anything in between. We must work such that we are eventually convinced that we can trust the system provided by the authors. It is easy to cook any result, to tweak it such that it is realistic, such that it appears consistent with whatever adjustment in the parameters, etc. There is no way we can detect all impostors. By default, however, I think there is a very high level of trust between us.
- The goal is to try to complete the reviews for the regular review deadline, to be able to give notifications at the regular notification deadline. If reviewing a repro paper turns out to be particularly complicated, then it is OK to miss that deadline. It simply means that this repro paper will not be included into the proceedings of the current year of ACM ICMR. Its reviewing will continue until a final decision is reached, with an aim for publishing the repro paper in the next year of ACM ICMR. If the review can not be finalized before the notification deadline for the next year of ACM ICMR too, however, then the paper is rejected.

### Reproducibility Review Process 
The reproducibility process should run as follows:

1. The chairs of the committee will team you with another reviewer who accepted that duty, as there must be at least two reviewers per reproducible paper. It’s a team, and close interactions between reviewers must be the standard. Quickly tell the chairs if any cooperation difficulty gets in your way.
2. The chairs of the committee will put you in touch with the authors of the paper. If necessary, initiate a discussion with the authors to ensure you are at the same page regarding specific details in the experiments that may not be clear.
3. After you receive access to code, datasets, and scripts, quickly verify that the submission is complete and has enough documentation before proceeding further.
4. When an issue appears, immediately contact the authors to help resolve it. The authors’ collaboration is both welcome and expected because they know and understand the specifics of their algorithms and code. In most cases, issues have to do with automating a script (e.g., making it path-independent) or dealing with dependencies.
5. The goal is both to go through the process of reproducing the results and to provide enough feedback to the authors so that they can create an easily shareable instance of their code and experiments.
6. When running experiments eliminate any interference in your systems, i.e., make sure, unless otherwise stated by the authors, that the machines used are dedicated to the reproducibility experiments.
7. If the results you gathered during the reproducibility process do not support the claims, contact the authors to address this. This may be due to issues that have to do with the set-up of the experiments or the hardware specifications.
8. The reviewing team writes a short report (1/2 to 1 page) to document the results and whether they were able to reproduce the results. If you can reproduce only part of the results please indicate that in your document. Also, make a note of any specific details regarding the set-up or analysis that are important. Communicate this report to the authors to make sure they think this is a fair result and take into account any suggestions.
9. That report is merged with the reproducible paper that was reviewed, and the two reviewers become co-authors on the resulting companion paper put inside the ACM DL in connection with the original contribution, to which the badge is attached.
10. If a paper cannot be reproduced, then contact the chairs. We will then dig into the problems.

## Reference

The process described in these pages was originally designed and implemented for ACM MM Reproducibility, see <https://project.inria.fr/acmmmreproducibility/review-guidelines/>.
