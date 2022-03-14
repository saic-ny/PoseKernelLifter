# PoseKernel Dataset

PoseKernel dataset is released in conjunction with our CVPR 2022 publication: PoseKernelLifter: Metric Lifting of 3D Human Pose using Sound


<br />

PoseKernel dataset composes of acoustic impulse response data for a variety of 3D human poses accross six different environments. We placed four pairs of co-located speakers and microphones in the environment, and one Kinect camera to capture the groundtruth 3D pose. We release the acoustic impulse response for each pair of speaker and microphone, as well as microphone and speaker's location, and the groundtruth 3D pose. All location related information are in the camera's frame.

## Directory Structure
    .
    ├── environment1                         
      ├── audio_sensor_loc.npy          # speaker, microphone location
      ├── 0
        ├── rir.npy                     # acoustic impulse response
        ├── gnd.npy                     # groundtruth 3D joint location
        ...
    ├── environment2                   
      ...
   
## Data format explanation
audio_sensor_loc.npy: four rows; each row is one pair of speaker/microhphone location in the camera's frame (speaker and microphone are co-located)<br />
rir.npy: four rows; each row is an impulse response (after compensating for the empty room's response) corresponding to one pair of speaker/mic. The speaker/mic order is the same as in audio_sensor_loc.npy. Each pair of speaker and microphone are synchronized. The sample rate of this impulse response is 96kHz. <br />
gnd.npy: groundtruth location of 3D body joints in the camera's frame. We use the joint order defined in Frankmocap. See https://github.com/facebookresearch/frankmocap/blob/main/docs/joint_order.md <br />