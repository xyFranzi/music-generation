## Dataset Download

The MAESTRO dataset (v2.0.0) can be downloaded here : [The MIDI Dataset](https://magenta.tensorflow.org/datasets/maestro#download)

After downloading, put all .mid files into one folder *dataset/maestro*

Also other datasets can be downloaded by:
```bash
$ sh dataset/script/{ecomp_piano_downloader, midi_world_downloader, ...}.sh
```

## Preprocessing Dataset

* In this repository using single track method.

```bash
$ python preprocess.py {midi_load_dir} {dataset_save_dir}
```

in this case:
  
```bash
$ python preprocess.py dataset/maestro dataset/processed_maestro
```

## Training

```bash
$ python train.py -c {config yml file 1} {config yml file 2} ... -m {model_dir}
```

in this case:

```bash
$ python train.py -c config/base.yml config/generate.yml config/train.yml -m model
```

* Parameters in .yml files adjusted.

## Generate Music

```bash
$ python generate.py -c {config yml file 1} {config yml file 2} -m {model_dir}
```

in this case:

```bash
$ python generate.py -c config/base.yml config/generate.yml -m model
```

