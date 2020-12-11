## Zachary Wharton, Ardhendu Behera, Yonghuai Liu and Nik Bessis 
**Department of Computer Science, Edge Hill University**


### Abstract

There is significant progress in recognizing traditional human activities from videos focusing on highly distinctive actions involving discriminative body movements, body-object and/or human-human interactions. Driver's activities are different since they are executed by the same subject with similar body parts movements, resulting in subtle changes. To address this, we propose a novel framework by exploiting the spatiotemporal attention to model the subtle changes. Our model is named Coarse Temporal Attention Network (CTA-Net), in which coarse temporal branches are introduced in a trainable glimpse network. The goal is to allow the glimpse to capture high-level temporal relationships, such as ‘during’, ‘before’ and ‘after’ by focusing on a specific part of a video. These branches also respect the topology of the temporal dynamics in the video, ensuring that different branches learn meaningful spatial and temporal changes. The model then uses an innovative attention mechanism to generate high-level action specific contextual information for activity recognition by exploring the hidden states of an LSTM. The attention mechanism helps in learning to decide the importance of each hidden state for the recognition task by weighing them when constructing the representation of the video. Our approach is evaluated on four publicly accessible datasets and significantly outperforms the state-of-the-art by a considerable margin with only RGB video as input.

### CTA-Net Model Architecture
Our CTA-Net is based on ResNet-50 architecture and uses visual attention in an innovative way to capture both subtle spatiotemporal changes and coarse ('before', 'during' and 'after') temporal relationships. It attends <i>visual cues specific to  temporal segments</i> to preserve the temporal ordering in a given video and then a temporal attention mechanism, which dictates how much to <i>attend</i> the <i>current visual cues conditioned on their temporal neighborhood contexts</i>.

<p align="center" width="100%">
    <img src="./full_image.jpg"><br>
    The proposed CTA-Net consists of - <b>a) Glimpse sensor:</b> Given an input video <i>v</i> consisting <i>T</i> frames, the sensor extract feature <i>x_t</i> for the frame located at time <i>t</i>, where <i>t=1 ... T</i>. <b>b) Self-Attention:</b> It captures important cues on activity-specific spatial changes. <b>c) Temporal Attention:</b> The module uses the internal state <i>h_t</i> of an LSTM (unrolled) that takes as input <i>x_t</i> and selectively focuses on the <i>h_t</i> to infer activity.
</p>


```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/ArdhenduBehera/abehera.github.io/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://docs.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
