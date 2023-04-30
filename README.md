# Lost.CU
 Lost.CU is a batch script that runs several programs that progressively degrades videos, developed as part of the art project MEMORIA.

# STATEMENT
MEMORIA is an immersive four-channel expanded cinema installation with custom software and hardware components. It combines ethnographic research, science fiction, and recombinatory forms of cinema that appropriate found or pirated footage. The work intertwines two narrative planes: the dystopian imagination of William Gibson’s Johnny Mnemonic (1981), one of the earliest cyberpunk short stories, and the real-world Cuban “offline internet”, the physical data distribution network Paquete Semanal. As a collaboration between a media artist, an anthropologist, and a Sci-Fi writer, MEMORIA is based on long-term ethnographic fieldwork on Cuban alternative data distribution networks.

To represent the memory loss of its protagonist, the work will slowly “die” over the course of the exhibition. For this we have developed a batch script that runs several programs that continuously manipulate the image quality of the videos. Over time the video devours itself through the constant process of faulty replication.

# TECHNICAL DESCRIPTION

Through the performance of Lost.CU the videos will slowly “die” over the course of the exhibition. Lost.CU executes various programs that continuously manipulate the video: FFMPG, for video and audio transcoding, and two custom programs written in Ruby: Datamosh, which deletes segments of the video so they can be overwritten afterwards, and Moshy, which overwrites these empty segments with information copied from random other parts of the video. This process gives the impression that the visual information in the videos is gradually lost and the image progressively degrades. However, the process does just the opposite. This automated, constant copying process not only corrupts the audiovisual material, but eventually also damages the hard disk where the project files are stored. Over time the video devours itself through the constant process of faulty replication, like a cancer that makes the cells inside the host grow in a random and uncontrolled way. The speed at which the material deteriorates is adjusted to the duration of the work’s exhibition.

# IMPLEMENTATION

The Memoria project is implemented using Python and the VLC media player. The main components of the project include:

```corrupt_video(input_file, output_file_template, initial_crf=30, noise_intensity=2)```

This function takes an input video file and applies a noise filter to it using FFmpeg. The corrupted video is saved as a temporary file with a new name specified by the output_file_template parameter. The original input file is then deleted, and the temporary file is renamed to the original file name.

```play_video(screen_number, video_file)```

This function plays a given video file on the VLC media player, using the specified screen number. The video is played in fullscreen mode, and the player is configured to loop the video and hide the video title. The function returns a subprocess.Popen object representing the running VLC process.

```process_videos()```

This function applies the corrupt_video() function to a set of input video files, creating a set of corrupted video files that will be played by the play_video() function.

```start_videos(video_files)```

This function starts a set of VLC media player instances, each playing one of the given video files using a unique screen number. The function returns a list of subprocess.Popen objects representing the running VLC processes.

```stop_videos(vlc_processes)```

This function stops a set of running VLC media player instances by killing their corresponding subprocess.Popen objects.

The main script for the project is memoria.py, which sets up the schedule for periodically corrupting and restarting the videos. The schedule is created using the schedule module, and the scheduled_task() function is called at a set time each day to stop the current videos, process new corrupted videos, and start playing them.

# USAGE
To use the Memoria project, you'll need to have Python and the VLC media player installed on your system. Clone the project repository, navigate to the project directory, and run the following command:

```python3 Lost-CU.py```

# In collaboration with:  
[Steffen Köhn](http://steffenkoehn.com/) 


# Software developer and programming
[Eduardo Pujol](https://github.com/kopekC)

- Audio channels configuration: [Jurij Podgoršek](https://github.com/g1smo)

# Hardware design
All hardware is housed in a custom case, a sculptural object in itself that was molded by using FOSS and 3D printed from recycled plastic filaments in collaboration with [COPINCHA](https://copincha.org/), a hackerspace in Havana that works with local materials and technologies.
