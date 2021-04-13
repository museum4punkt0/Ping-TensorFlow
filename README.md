# Image Classification Tutorial - TensorFlow!
You can generate both mobile or backend graphs with files is directories of this repo

 ## Setup and Install
 - Python 2.7
 - clone the project
 - add folders with images to classify into a dataset/ directory, forlders names results into labels name file (see two example directories in dataset)
 - cd backend_graph/ or mobile_graph/ 
 
 - Create virtual environment, if you want using virtualenv command
 - Install dependent libararies
   > pip install -r requirements.txt
 
 ## Train your model using our processed dataset
 - Run the below command to train your model using different architectures.
   For mobile graph
   > python retrain.py \
    --image_dir /home/user/Documents/projects/deep-learning/dataset/ \
    --architecture=mobilenet_1.0_224 \
    --output_graph=trained_model/museum_mobile_v1_224_graph.pb \
    --output_labels=labels/museum_mobile_1_224_labels_2.txt

   For backend graph
   > python retrain.py \
    --image_dir /home/user/Documents/projects/deep-learning/dataset/ \
    --tfhub_module https://tfhub.dev/google/imagenet/mobilenet_v2_100_224/feature_vector/2 \
    --output_graph=trained_model/example_backend_mobile_v2_224_graph.pb \
    --output_labels=labels/example_backend_mobile_v2_224_labels.txt 
         

  ## Test your model
  - Run the below python script to classify your test images based on our pre-trained model.
  > python label_image.py \
    --graph=trained_model/example_backend_mobile_v2_224_graph.pb \
    --labels=labels/example_backend_mobile_v2_224_labels.txt \
    --image=label_image/image you want to classify.jpg \
    --input_layer=Placeholder \
    --output_layer=final_result \
    --input_mean=128 \
    --input_std=128 \
    --input_width=224 \
    --input_height=224

 ## Done.
  
# Lizenz 

Ping! Die Museumsapp Copyright © 2021 Stiftung Humboldt Forum im Berliner Schloss; entwickelt von Humboldt Innovation GmbH, Thomas Lilge, Christian Stein, im Rahmen des Verbundprojekts museum4punkt0, weitentwickelt in Kooperation mit dem Badischen Landesmuseum im Rahmen des Projekts Creative Collections.

This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see <https://www.gnu.org/licenses/>.

[![LICENSE.md](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://github.com/museum4punkt0/Mein-Objekt-Backend/blob/master/LICENSE.md)

[https://www.tensorflow.org/](Tensorflow) ist unter Apache 2.0 lizensiert.

[https://tfhub.dev/](Tensorflow models) sind unter Apache 2.0 lizensiert.
 
