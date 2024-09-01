# Plant Disease Classification

> Model Used: ResNet12
> 
> Accuracy: 99.3%

## Links:
Dataset - [Dataset](https://www.kaggle.com/datasets/vipoooool/new-plant-diseases-dataset)
<br>
NoteBook - [NoteBook](https://www.kaggle.com/code/dhaks13/plant-disease-classification)

## Model :-
### **ResNeT-12 Varient architecture**
**ResNet**: The main ResNet architecture. It builds the network using a series of residual blocks.

**So what is residual blocks in residual learning?:**
>**Residual Blocks**: The core idea of ResNet is the use of residual blocks, which include skip (or shortcut) connections. These connections allow the network to learn residual mappings rather than the direct mapping, making it easier to train very deep networks.

>**Skip Connections**: These connections bypass one or more layers, allowing the network to learn an identity function if it is optimal, thus preventing the degradation problem in very deep networks.

**Convolution Block**: A single convolutional layer followed by a batch normalization and ReLU activation.

![Convolution Block](https://github.com/user-attachments/assets/d3de83b7-95ac-4b7a-8b59-450302209800)

**BasicBlock**: Defines the residual block used in ResNet-12. Each block consists of two convolutional layers.

![BasicBlock](https://github.com/user-attachments/assets/25b3b8f3-dcea-4b67-8a8a-e87caa517ada)

**Residual Blocks**: 

![Residual Blocks](https://github.com/user-attachments/assets/61fa893c-302e-43d3-a161-fb1b97f82559)

·  **Average Pooling**: Applied before the final fully connected layer.

·  **Fully Connected Layer**: The final classification layer.

<hr>
<br>
<br>
<h2>Model Summary</h2>
    <table>
        <thead>
            <tr>
                <th>Layer (type)</th>
                <th>Output Shape</th>
                <th>Param #</th>
            </tr>
        </thead>
        <tbody>
            <tr><td>Conv2d-1</td><td>[-1, 64, 256, 256]</td><td>1,792</td></tr>
            <tr><td>BatchNorm2d-2</td><td>[-1, 64, 256, 256]</td><td>128</td></tr>
            <tr><td>ReLU-3</td><td>[-1, 64, 256, 256]</td><td>0</td></tr>
            <tr><td>Convolution_Block-4</td><td>[-1, 64, 256, 256]</td><td>0</td></tr>
            <tr><td>Conv2d-5</td><td>[-1, 64, 256, 256]</td><td>36,928</td></tr>
            <tr><td>BatchNorm2d-6</td><td>[-1, 64, 256, 256]</td><td>128</td></tr>
            <tr><td>ReLU-7</td><td>[-1, 64, 256, 256]</td><td>0</td></tr>
            <tr><td>Convolution_Block-8</td><td>[-1, 64, 256, 256]</td><td>0</td></tr>
            <tr><td>Conv2d-9</td><td>[-1, 64, 256, 256]</td><td>36,928</td></tr>
            <tr><td>BatchNorm2d-10</td><td>[-1, 64, 256, 256]</td><td>128</td></tr>
            <tr><td>ReLU-11</td><td>[-1, 64, 256, 256]</td><td>0</td></tr>
            <tr><td>Convolution_Block-12</td><td>[-1, 64, 256, 256]</td><td>0</td></tr>
            <tr><td>Residual_Block-13</td><td>[-1, 64, 256, 256]</td><td>0</td></tr>
            <tr><td>Conv2d-14</td><td>[-1, 128, 256, 256]</td><td>73,856</td></tr>
            <tr><td>BatchNorm2d-15</td><td>[-1, 128, 256, 256]</td><td>256</td></tr>
            <tr><td>ReLU-16</td><td>[-1, 128, 256, 256]</td><td>0</td></tr>
            <tr><td>Convolution_Block-17</td><td>[-1, 128, 256, 256]</td><td>0</td></tr>
            <tr><td>MaxPool2d-18</td><td>[-1, 128, 64, 64]</td><td>0</td></tr>
            <tr><td>Conv2d-19</td><td>[-1, 128, 64, 64]</td><td>147,584</td></tr>
            <tr><td>BatchNorm2d-20</td><td>[-1, 128, 64, 64]</td><td>256</td></tr>
            <tr><td>ReLU-21</td><td>[-1, 128, 64, 64]</td><td>0</td></tr>
            <tr><td>Convolution_Block-22</td><td>[-1, 128, 64, 64]</td><td>0</td></tr>
            <tr><td>Conv2d-23</td><td>[-1, 128, 64, 64]</td><td>147,584</td></tr>
            <tr><td>BatchNorm2d-24</td><td>[-1, 128, 64, 64]</td><td>256</td></tr>
            <tr><td>ReLU-25</td><td>[-1, 128, 64, 64]</td><td>0</td></tr>
            <tr><td>Convolution_Block-26</td><td>[-1, 128, 64, 64]</td><td>0</td></tr>
            <tr><td>Residual_Block-27</td><td>[-1, 128, 64, 64]</td><td>0</td></tr>
            <tr><td>Conv2d-28</td><td>[-1, 256, 64, 64]</td><td>295,168</td></tr>
            <tr><td>BatchNorm2d-29</td><td>[-1, 256, 64, 64]</td><td>512</td></tr>
            <tr><td>ReLU-30</td><td>[-1, 256, 64, 64]</td><td>0</td></tr>
            <tr><td>Convolution_Block-31</td><td>[-1, 256, 64, 64]</td><td>0</td></tr>
            <tr><td>MaxPool2d-32</td><td>[-1, 256, 16, 16]</td><td>0</td></tr>
            <tr><td>Conv2d-33</td><td>[-1, 256, 16, 16]</td><td>590,080</td></tr>
            <tr><td>BatchNorm2d-34</td><td>[-1, 256, 16, 16]</td><td>512</td></tr>
            <tr><td>ReLU-35</td><td>[-1, 256, 16, 16]</td><td>0</td></tr>
            <tr><td>Convolution_Block-36</td><td>[-1, 256, 16, 16]</td><td>0</td></tr>
            <tr><td>Conv2d-37</td><td>[-1, 256, 16, 16]</td><td>590,080</td></tr>
            <tr><td>BatchNorm2d-38</td><td>[-1, 256, 16, 16]</td><td>512</td></tr>
            <tr><td>ReLU-39</td><td>[-1, 256, 16, 16]</td><td>0</td></tr>
            <tr><td>Convolution_Block-40</td><td>[-1, 256, 16, 16]</td><td>0</td></tr>
            <tr><td>Residual_Block-41</td><td>[-1, 256, 16, 16]</td><td>0</td></tr>
            <tr><td>Conv2d-42</td><td>[-1, 256, 16, 16]</td><td>590,080</td></tr>
            <tr><td>BatchNorm2d-43</td><td>[-1, 256, 16, 16]</td><td>512</td></tr>
            <tr><td>ReLU-44</td><td>[-1, 256, 16, 16]</td><td>0</td></tr>
            <tr><td>Convolution_Block-45</td><td>[-1, 256, 16, 16]</td><td>0</td></tr>
            <tr><td>MaxPool2d-46</td><td>[-1, 256, 4, 4]</td><td>0</td></tr>
            <tr><td>Conv2d-47</td><td>[-1, 512, 4, 4]</td><td>1,180,160</td></tr>
            <tr><td>BatchNorm2d-48</td><td>[-1, 512, 4, 4]</td><td>1,024</td></tr>
            <tr><td>ReLU-49</td><td>[-1, 512, 4, 4]</td><td>0</td></tr>
            <tr><td>Convolution_Block-50</td><td>[-1, 512, 4, 4]</td><td>0</td></tr>
            <tr><td>MaxPool2d-51</td><td>[-1, 512, 1, 1]</td><td>0</td></tr>
            <tr><td>Flatten-52</td><td>[-1, 512]</td><td>0</td></tr>
            <tr><td>Linear-53</td><td>[-1, 38]</td><td>19,494</td></tr>
        </tbody>
    </table>
    <hr>
<p>Total params: 3,713,958</p>
<p>Trainable params: 3,713,958</p>
<p>Non-trainable params: 0</p>
<hr>
<p>Input size (MB): 0.75</p>
<p>Forward/backward pass size (MB): 751.29</p>
<p>Params size (MB):  14.17</p>
<p>Estimated Total Size (MB): 766.21</p>
<hr>
<br>
<h2>Conclusion</h2>
<p>ResNets achieve outstanding results in image classification when parameters are adjusted and techniques such as learning rate scheduling, gradient clipping, and weight decay are applied. With these optimizations, the model can predict every image in the test set with an impressive accuracy of 99.3% and no errors.</p>
<hr>
<br>

# **References**
* [PDC ResNet Implementation](https://www.kaggle.com/code/atharvaingle/plant-disease-classification-resnet-99-2)
* [PyTorch docs](http://pytorch.org)
* [Other Notebooks](https://github.com/Dhaks13/My_DL_Works/)
