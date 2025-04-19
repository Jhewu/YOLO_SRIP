# YOLO Stream River Image Processor (YOLO-SRIP)

This is a modified version of the **Stream River Image Processor (SRIP)**, originally developed by Professor Timothy J. Becker. This version incorporates **YOLO Auto Cropping** for river images using YOLO model weights.

Check the **sample outputs** and **sample 2018 data** provided in the working directory.

---

## How To Use

### 1. Create a New Conda Environment and Install the Requirements

```bash
conda create --name yolo_srip python=3.12
pip install -r requirements.txt
conda activate yolo_srip
```

### 1.5 Install and Build PyTorch

Check this link: https://pytorch.org/get-started/locally/

### 2. Run yolo_srip.py to process the data and perform auto-crop with YOLO. Use the -h handle to check for command line arguments 

```bash
python3 yolo_srip.py \
--in_dir ./sample_2018_data \
--out_dir ./out_dir \
--width 600 \
--height 200 \
--model_dir model/best.pt \
--window_size 32 \
--conf 0.7
```

### 3. Run stream_river_image_processor.py to run SRIP workflow. 

```bash
python3 stream_river_image_processor.py \
--in_dir ./out_dir/passed \
--out_dir ./out_dir \
--res 600,200 \
--enh_hrs 2 \
--agg_hrs 2 \
--winsize 2 \
--cpus 16
```