# The NSynth Dataset
Apr 5, 2017 
• NSynth

A large-scale and high-quality dataset of annotated musical notes.

## Motivation
 Recent breakthroughs in generative modeling of images have been predicated on the availability of high-quality and large-scale datasebts such as MNIST, CIFAR and ImageNet. We recognized the need for an audio dataset that was as approachable as those in the image domain.
Audio signals found in the wild contain multi-scale dependencies that prove particularly difficult to model, leading many previous efforts at data-driven audio synthesis to focus on more constrained domains such as texture synthesis or training small parametric models.
We encourage the broader community to use NSynth as a benchmark and entry point into audio machine learning. We also view NSynth as a building block for future datasets and envision a high-quality multi-note dataset for tasks like generation and transcription that involve learning complex language-like dependencies.

## Description
NSynth is an audio dataset containing 305,979 musical notes, each with a unique pitch, timbre, and envelope. For 1,006 instruments from commercial sample libraries, we generated four second, monophonic 16kHz audio snippets, referred to as notes, by ranging over every pitch of a standard MIDI pian o (21-108) as well as five different velocities (25, 50, 75, 100, 127). The note was held for the first three seconds and allowed to decay for the final second.
Some instruments are not capable of producing all 88 pitches in this range, resulting in an average of 65.4 pitches per instrument. Furthermore, the commercial sample packs occasionally contain duplicate sounds across multiple velocities, leaving an average of 4.75 unique velocities per pitch.
We also annotated each of the notes with three additional pieces of information based on a combination of human evaluation and heuristic algorithms:

 - Source: The method of sound production for the note’s instrument. This can be one of acoustic or electronic for instruments that were recorded from acoustic or electronic instruments, respectively, or synthetic for synthesized instruments. See their frequencies below.

 - Family: The high-level family of which the note’s instrument is a member. Each instrument is a member of exactly one family. See the complete list and their frequencies below.

 - Qualities: Sonic qualities of the note. See the quality descriptions and their co-occurrences below. Each note is annotated with zero or more qualities.
 
## Format

### Files
 The NSynth dataset can be download in two formats:
 - TFRecord files of serialized TensorFlow Example protocol buffers with one Example proto per note.
 - JSON files containing non-audio features alongside 16-bit PCM WAV audio files.

The full dataset is split into three sets:

 - Train [[tfrecord](http://download.magenta.tensorflow.org/datasets/nsynth/nsynth-train.tfrecord) | [json/wav](http://download.magenta.tensorflow.org/datasets/nsynth/nsynth-train.jsonwav.tar.gz)]: A training set with 289,205 examples. Instruments do not overlap with valid or test.
 - Valid [[tfrecord](http://download.magenta.tensorflow.org/datasets/nsynth/nsynth-valid.tfrecord) | [json/wav](http://download.magenta.tensorflow.org/datasets/nsynth/nsynth-valid.jsonwav.tar.gz)]: A validation set with 12,678 examples. Instruments do not overlap with train.
 - Test  [[tfrecord](http://download.magenta.tensorflow.org/datasets/nsynth/nsynth-test.tfrecord)  | [json/wav](http://download.magenta.tensorflow.org/datasets/nsynth/nsynth-test.jsonwav.tar.gz)]: A test set with 4,096 examples. Instruments do not overlap with train.

## License

The dataset is made available by Google Inc. under a Creative Commons Attribution 4.0 International (CC BY 4.0) license.

## How to Cite

If you use the NSynth dataset in your work, please cite the paper where it was introduced:

Jesse Engel, Cinjon Resnick, Adam Roberts, Sander Dieleman, Douglas Eck,
  Karen Simonyan, and Mohammad Norouzi. "Neural Audio Synthesis of Musical Notes
  with WaveNet Autoencoders." 2017.
You can also use the following BibTeX entry:

@misc{nsynth2017,
    Author = {Jesse Engel and Cinjon Resnick and Adam Roberts and
              Sander Dieleman and Douglas Eck and Karen Simonyan and
              Mohammad Norouzi},
    Title = {Neural Audio Synthesis of Musical Notes with WaveNet Autoencoders},
    Year = {2017},
    Eprint = {arXiv:1704.01279},
}

## Updates

04-10-2017: Removed 64 duplicate notes from train set.
