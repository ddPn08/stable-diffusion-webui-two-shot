# Latent Couple extension (two shot diffusion port)
This extension is an extension of the built-in Composable Diffusion.
This allows you to determine the region of the latent space that reflects your subprompts.

## Prerequisite
This extension need to apply cfg_denoised_callback-ea9bd9fc.patch (as of Feb 5, 2023 origin/HEAD commit ea9bd9fc).
```
git apply --ignore-whitespace extensions/stable-diffusion-webui-two-shot/cfg_denoised_callback-ea9bd9fc.patch
```

## How to use
todo

If you want to disable the effect of this extension without uninstalling it, set the end at step to 0.

## Extra generation params
Extra generation params provided by this extension are saved as PNG Info in the output file.
```
Latent Couple: "divisions=1:1,1:2,1:2 positions=0:0,0:0,0:1 weights=0.2,0.8,0.8 end at step=20"
```

## Examples
parameters
```
((ultra-detailed)), ((illustration)), 2girls
AND ((ultra-detailed)), ((illustration)), 2girls, black hair
AND ((ultra-detailed)), ((illustration)), 2girls, blonde hair
Negative prompt: (low quality, worst quality:1.4)
Steps: 28, Sampler: Euler a, CFG scale: 5, Seed: 722014241, Size: 512x512, Model hash: 3f64f3baf5, Model: Anything-v3.0-fp16, ENSD: 31337, Latent Couple: "divisions=1:1,1:2,1:2 positions=0:0,0:0,0:1 weights=0.2,0.8,0.8 end at step=20", Eta: 0.67
```
outouts
- end at step=20 https://imgur.com/oD50YlA
- end at step=4 https://imgur.com/I7Jagdw
- end at step=0 https://imgur.com/WQex89y

## Credits
- two shot diffusion.ipynb https://colab.research.google.com/drive/1UdElpQfKFjY5luch9v_LlmSdH7AmeiDe?usp=sharing
