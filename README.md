# Kohya Trainer V13
| Notebook Name | Description | Link | Old Commit |
| --- | --- | --- | --- |
| [Kohya LoRA Dreambooth](https://github.com/kasem6746/Cv13-test/blob/main/kohya-LoRA-dreambooth.ipynb) | LoRA Training (Dreambooth method) | [![](https://img.shields.io/static/v1?message=Open%20in%20Colab&logo=googlecolab&labelColor=5c5c5c&color=0f80c1&label=%20&style=for-the-badge)](https://colab.research.google.com/github/kasem6746/Cv13-test/blob/main/kohya-LoRA-dreambooth.ipynb) | [![](https://img.shields.io/static/v1?message=Oldest%20Version&logo=googlecolab&labelColor=5c5c5c&color=e74c3c&label=%20&style=for-the-badge)](https://colab.research.google.com/github/Linaqruf/kohya-trainer/blob/bc0892647cb17492a106ad1d05716e091eda13f6/kohya-LoRA-dreambooth.ipynb) | 
| [Kohya LoRA Fine-Tuning](https://github.com/Linaqruf/kohya-trainer/blob/main/kohya-LoRA-finetuner.ipynb) | LoRA Training (Fine-tune method) | [![](https://img.shields.io/static/v1?message=Open%20in%20Colab&logo=googlecolab&labelColor=5c5c5c&color=0f80c1&label=%20&style=for-the-badge)](https://colab.research.google.com/github/Linaqruf/kohya-trainer/blob/main/kohya-LoRA-finetuner.ipynb) | [![](https://img.shields.io/static/v1?message=Oldest%20Version&logo=googlecolab&labelColor=5c5c5c&color=e74c3c&label=%20&style=for-the-badge)](https://colab.research.google.com/github/Linaqruf/kohya-trainer/blob/fb96280233d3434819ba5850b2c968150c4720f7/kohya-LoRA-finetuner.ipynb) | 
| [Kohya Trainer](https://github.com/Linaqruf/kohya-trainer/blob/main/kohya-trainer.ipynb) | Native Training | [![](https://img.shields.io/static/v1?message=Open%20in%20Colab&logo=googlecolab&labelColor=5c5c5c&color=0f80c1&label=%20&style=for-the-badge)](https://colab.research.google.com/github/Linaqruf/kohya-trainer/blob/main/kohya-trainer.ipynb) | [![](https://img.shields.io/static/v1?message=Oldest%20Version&logo=googlecolab&labelColor=5c5c5c&color=e74c3c&label=%20&style=for-the-badge)](https://colab.research.google.com/github/Linaqruf/kohya-trainer/blob/21ad4942a917d3fd1ad6c03d87d16677b427254b/kohya-trainer.ipynb) | 
| [Kohya Dreambooth](https://github.com/Linaqruf/kohya-trainer/blob/main/kohya-dreambooth.ipynb) | Dreambooth Training | [![](https://img.shields.io/static/v1?message=Open%20in%20Colab&logo=googlecolab&labelColor=5c5c5c&color=0f80c1&label=%20&style=for-the-badge)](https://colab.research.google.com/github/Linaqruf/kohya-trainer/blob/main/kohya-dreambooth.ipynb) | [![](https://img.shields.io/static/v1?message=Oldest%20Version&logo=googlecolab&labelColor=5c5c5c&color=e74c3c&label=%20&style=for-the-badge)](https://colab.research.google.com/github/Linaqruf/kohya-trainer/blob/9c7f891981bee92cc7690f2094f892c46feb99e2/kohya-dreambooth.ipynb) | 
| [Fast Kohya Trainer](https://github.com/Linaqruf/kohya-trainer/blob/main/fast-kohya-trainer.ipynb) `NEW`| Easy 1-click LoRA & Native Training| [![](https://img.shields.io/static/v1?message=Open%20in%20Colab&logo=googlecolab&labelColor=5c5c5c&color=0f80c1&label=%20&style=for-the-badge)](https://colab.research.google.com/github/Linaqruf/kohya-trainer/blob/main/fast-kohya-trainer.ipynb) |
| [Cagliostro Colab UI](https://github.com/Linaqruf/sd-notebook-collection/blob/main/cagliostro-colab-ui.ipynb) `NEW`| A Customizable Stable Diffusion Web UI| [![](https://img.shields.io/static/v1?message=Open%20in%20Colab&logo=googlecolab&labelColor=5c5c5c&color=0f80c1&label=%20&style=for-the-badge)](https://colab.research.google.com/github/Linaqruf/sd-notebook-collection/blob/main/cagliostro-colab-ui.ipynb) | 

## Updates
##### v13 (25/02):
__What Changes?__
- Of course refactoring, cleaning and make the code and cells more readable and easy to maintain.
  - Moved `Login to Huggingface Hub` to `Deployment` section, in the same cell with defining repo.
  - Merged `Install Kohya Trainer`, `Install Dependencies`, and `Mount Drive` cells
  - Merged `Dataset Cleaning` and `Convert RGB to RGBA` cells
  - Deleted `Image Upscaler` cell, because bucketing automatically upscale your dataset (converted to image latents) to `min_bucket_reso` value.
  - Deleted `Colab Ram Patch` because now you can set `--lowram` in the training script.
  - Revamped `Unzip dataset` cell to make it look simpler
- Added xformers pre-compiled wheel for `A100` 
- Revamped `Pretrained Model` section
  - Deleted some old pretrained model
  - Added `Anything V3.3`, `Chilloutmix`, and `Counterfeit V2.5` as new pretrained model for SD V1.x based model
  - Added `Replicant V1.0`, `WD 1.5 Beta` and `Illuminati Diffusion V1` as new pretrained model for SD V2.x 768v based model
  - Changed `Stable Diffusion 1.5` pretrained model to pruned one.
- Changed Natural Language Captioning back from GIT to BLIP with `beam_search` enabled by default
- Revamped Image Scraper from simple to advanced, added new feature such as:
  - Added `safebooru` to booru list
  - Added `custom_url` option, so you can copy and paste the url instead of specify which booru sites and tags to scrape
  - Added `user_agent` field, because you can't access some image board with default user_agent
  - Added `limit_rate` field to limit your count
  - [Experimental] Added `with_aria2c` to scrape your dataset, not a wrapper, just a simple trick to extract urls with `gallery-dl` and download them with aria2c instead. Fast but seems igonoring `--write-tags`.
  - All downloaded tags now saved with `.txt` format instead of `.jpg.txt`
  - Added `additional_arguments` to make it more flexible if you want to try other args
- Revamped `Append Custom Tag` cell
  - Create new caption file for every image file based on extension provided (`.txt/.caption`) if you didn't want to use BLIP or WD Tagger
  - Added `--keep_tokens` args to the cell
- Revamped `Training Model` section. 
  - Revamped `prettytable` for easier maintenance and bug fixing
  - Now it has 4 major cell:
    - Folder Config
      - To specify `v2`, `v2_parameterization` and all important folder and project_name
    - LoRA and Optimizer Config
      - Only `Optimizer Config` for notebook outside LoRA training
      - All about Optimizer, `learning_rate` and `lr_scheduler` goes here
      - Added new Optimizer from latest kohya-ss/sd-script, all available optimizer : `"AdamW", "AdamW8bit", "Lion", "SGDNesterov", "SGDNesterov8bit", "DAdaptation", "AdaFactor"
      - Currently you can't use `DAdaptation` if you're in Colab free tier because it need more VRAM
      - Added `--optimizer_args` for custom args, useful if you want to try adjusting weight decay, betas etc
    - Dataset Config
      - Only available for Dreambooth method notebook, it basically bucketing cell for Dreambooth.
      - Added `caption dropout`, you can drop your caption or tags by adjusting dropout rates.
      - Added `--bucket_reso_steps` and `--bucket_no_upscale`
    - Training Config
      - Added `--noise_offset`, read [Diffusion With Offset Noise](https://www.crosslabs.org//blog/diffusion-with-offset-noise)
      - Added `--lowram` to load the model in VRAM instead of CPU
- Revamped `Convert Diffusers to Checkpoint` cell, now it's more readable.
- Fixing bugs when `output_dir` located in google drive, it assert an error because of something like `/content/drive/dreambooth_cmd.yaml` which is forbidden, now instead of saved to `{output_dir}`, now training args history are saved to `{training_dir}`
