## Detection, Segmentation, and 3D Pose Estimation of Surgical Tools Using Deep Convolutional Neural Networks and Algebraic Geometry
#### The directroy tree of this repository is given below-

![DirectoryTreeDiagram](https://user-images.githubusercontent.com/32570071/58830739-492f0c00-864b-11e9-96ec-18dc0f05e404.png)


In this project, we present deep convolution neural network (DCNN) for simultaneously getting surgical instrument segmentation and geometric features for 3D pose estimation to solve the current ambiguities of AR based application in MIS. Additionally, we add detection sub-network to our SIMO-DCNN to get the tool flag. Tool flag will provide the constrain of estimating pose or not. The proposed network with different responsible sub-networks has been trained in an end-to-end fashion and each sub-network of the SIMO-DCNN has different loss functions to get responsible output.  We validate our proposed approach on both ex-vivo and in-vivo laparoscopic images where we are able to reach improved results over existing state-of-the-art approaches on the same dataset. The geometric features obtained from the proposed SIMO network are used to estimate the 3D pose of surgical instruments by geometric solver. <br>

![SIMO](https://user-images.githubusercontent.com/32570071/58485449-5f792b80-8164-11e9-9296-10ed923694f5.png)
Figure: The pipeline of the proposed framework for concurrent detection, segmentation, and geometric feature extraction for 3D pose estimation of surgical instrument.

The pictorial presentation of overall pipeline that has been accomplished is shown in above figure.  Firstly, input images are feed to CRB block which is a bunch of convolution  and relu activation  with  sub-sampling  and  is  shared  by  all  others  sub-networks for detection, segmentation and regression simultaneously.  FCS is the fully connected layer followed by the softmax classifier that provides the information about the tool presence in the image frame and termed as detection sub-network. If the detected tool flag is yes from the detection sub-network, the pose of the surgical tool will be estimated and vice-versa. DRBS named as segmentation sub-network and DRB named as regression sub-network are the bunch deconvolution for semantic tissue or instrument pixels labelling and the regression to get three geometric features for pose estimation respectively.  

## Annotation pipeline
For the annotation, we have used ImageJ software and basic image processing methods. Firstly, the ROI of the tool is selected from ImageJ software and then below block diagram has been used to get binary mask of the surgical tool. 
![annotation](https://user-images.githubusercontent.com/32570071/58098941-dc435d00-7bda-11e9-8845-1f16a9945198.JPG)

Simultaneously, during the ROI selection, five points are selected and extracted as CSV and then basic image processing methods has been used to create the edge-line, mid-line and tip-point. The selected five points are presented below.

![Point Selection](https://user-images.githubusercontent.com/32570071/58100378-ce430b80-7bdd-11e9-93bd-b573ca924951.jpg)


The example of our annotated image along with corresponding binary mask, edge-line, mid-line and tip-point is shown below.
![Annotated Geometric Features](https://user-images.githubusercontent.com/32570071/58099671-6b04a980-7bdc-11e9-83b4-c680de96beba.png)

MICCAI 2015 Endoscopic Vision Challenge - Instrument Segmentation and Tracking Sub-challenge <br>
https://endovissub-instrument.grand-challenge.org/

#### Written by-
#### Md. Kamrul Hasan 
#### Erasmus Scholar on Medical Imaging and Application (MAIA) [http://maiamaster.udg.edu/]
#### For more details write me at kamruleeekuet@gmail.com
