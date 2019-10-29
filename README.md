# Capsule-Forensics

Implementation of the paper:  <a href="https://arxiv.org/abs/1910.12467">Use of a Capsule Network to Detect Fake Images and Videos</a>, which is an **updated version** of the previous work:  <a href="https://arxiv.org/abs/1810.11215">Capsule-Forensics: Using Capsule Networks to Detect Forged Images and Videos</a> (ICASSP 2019).

You can clone this repository into your favorite directory:

    $ git clone https://github.com/nii-yamagishilab/Capsule-Forensics-v2

## Requirement
- PyTorch 1.3
- TorchVision
- scikit-learn
- Numpy

## Project organization
- Databases folder, where you can place your training, evaluation, and test set:

      ./databases/<faceforensicspp; cgvsphoto_patches; cgvsphoto_full; replay_attack>/<train; validation; test>
- Checkpoint folder, where the training outputs will be stored:

      ./checkpoints/<binary_faceforensicspp; multiclass_faceforensicspp; cgvsphoto; replay_attack>

Pre-trained models for the FaceForensics++ database (includes Real, DeepFakes, Face2Face, and FaceSwap), the CGvsPhoto database, and the Replay-Attack database (with settings described in our paper) are provided in the checkpoints folder.

## Databases

In case of the FaceForensics++ database, it need to be **pre-processed to crop facial area**.

## Training
**Note**: Parameters with detail explanation could be found in the corresponding source code.

Training the Capsule-Forensics-v2 using binary classification on the FaceForensics++ database:

    $ python train_binary_ffpp.py
   
Training the Capsule-Forensics-v2 using multiclass classification on the FaceForensics++ database:

    $ python train_multiclass_ffpp.py
    
Training the Capsule-Forensics-v2 on the CGvsPhoto database:

    $ python train_cgvsphoto.py
    
Training the Capsule-Forensics-v2 on the Idiap Replay-Attack database:

    $ python train_replay_attack.py

## Evaluating
**Note**: Parameters with detail explanation could be found in the corresponding source code.

### FaceForensics++ database (includes Real, DeepFakes, Face2Face, and FaceSwap)
Binary classification on images:

    $ python test_binary_ffpp.py

Binary classification on videos (extracted as frames):

    $ python test_vid_binary_ffpp.py
    
Multiclass classification on images:

    $ python test_multiclass_ffpp.py
    
Multiclass classification on images with detail results on each class:

    $ python test_multiclass_detail_ffpp.py

Multiclass classification on videos (extracted as frames):

    $ python test_vid_multiclass_ffpp.py
    
### CGvsPhoto database

Testing on patches:

    $ python test_cgvsphoto.py

Testing on full images:

    $ python test_cgvsphoto_full.py

### Idiap Replay-Attack database
Testing on images:

    $ python test_replay_attack.py

## Authors
- Huy H. Nguyen (https://researchmap.jp/nhhuy/?lang=english)
- Junichi Yamagishi (https://researchmap.jp/read0205283/?lang=english)
- Isao Echizen (https://researchmap.jp/echizenisao/?lang=english)

## Acknowledgement
This research was supported by JSPS KAKENHI Grants JP16H06302 and JP18H04120 and by JST CREST Grant JPMJCR18A6, Japan.

## Reference
H. H. Nguyen, J. Yamagishi, and I. Echizen, “Use of a Capsule Network to Detect Fake Images and Videos,” arXiv preprint arXiv:1910.12467. 2019 Oct 29.
