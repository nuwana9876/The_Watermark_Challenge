# The_Watermark_Challenge

### [Home Page](https://machinehack.com/hackathons/the_watermark_challenge/overview)
<img width="800" alt="watermarkchallenge" src="https://github.com/nuwana9876/The_Watermark_Challenge/assets/78463348/9cb1c291-a656-467c-b94a-c2013fba61ef">

### [Leaderboard](https://machinehack.com/hackathons/the_watermark_challenge/leaderboard)
<img width="800" alt="result" src="https://github.com/nuwana9876/The_Watermark_Challenge/assets/78463348/ed0b33c9-d8ff-4e26-ba35-825f794b3141">

### Train & Parameter

- Image size : 1024 x 1024

- Image processing:
- Train - Resize, RandomRotation , Normalize (ImageNet default [0.485, 0.456, 0.406], [0.229, 0.224, 0.225])
- Test - Resize, Normalize (ImageNet default [0.485, 0.456, 0.406], [0.229, 0.224, 0.225])

- Train data was used 80% as Train and 20% as Validation data.

![image](https://github.com/nuwana9876/The_Watermark_Challenge/assets/78463348/64521294-157b-49ce-b20e-8a37021c280f)

- The model is convnext_large_in22k, and we used timm to load and use the model.
- Added three fc layers and ReLU(), Dropout() in the middle.

- criterion = torch.nn.CrossEntropyLoss()
- optimizer = optim.AdamW(params=model.parameters(), lr=0.2e-5)
- scheduler = torch.optim.lr_scheduler.ReduceLROnPlateau(optimizer, mode='max', factor=0.5, patience=2, threshold_mode='abs', min_lr=1e-8, verbose=True)

#### Parameter
- BATCH_SIZE = 4
- Num epochs = 50
- Patience = 6 (early stopping)

Finally, the model was put in Watermarks Predictor to return the results.

[Watermark-detection-github](https://github.com/boomb0om/watermark-detection)

The Watermark Predictor used the link code.
