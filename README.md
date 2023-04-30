# Lost.CU
 Lost.CU is a batch script that runs several programs that progressively degrades videos, developed as part of the art project MEMORIA.

# STATEMENT
MEMORIA is an immersive four-channel expanded cinema installation with custom software and hardware components. It combines ethnographic research, science fiction, and recombinatory forms of cinema that appropriate found or pirated footage. The work intertwines two narrative planes: the dystopian imagination of William Gibson’s Johnny Mnemonic (1981), one of the earliest cyberpunk short stories, and the real-world Cuban “offline internet”, the physical data distribution network Paquete Semanal. As a collaboration between a media artist, an anthropologist, and a Sci-Fi writer, MEMORIA is based on long-term ethnographic fieldwork on Cuban alternative data distribution networks.

To represent the memory loss of its protagonist, the work will slowly “die” over the course of the exhibition. For this we have developed a batch script that runs several programs that continuously manipulate the image quality of the videos. Over time the video devours itself through the constant process of faulty replication.

# TECHNICAL DESCRIPTION

Through the performance of Lost.CU the videos will slowly “die” over the course of the exhibition. Lost.CU executes various programs that continuously manipulate the video: FFMPG, for video and audio transcoding, and two custom programs written in Ruby: Datamosh, which deletes segments of the video so they can be overwritten afterwards, and Moshy, which overwrites these empty segments with information copied from random other parts of the video. This process gives the impression that the visual information in the videos is gradually lost and the image progressively degrades. However, the process does just the opposite. This automated, constant copying process not only corrupts the audiovisual material, but eventually also damages the hard disk where the project files are stored. Over time the video devours itself through the constant process of faulty replication, like a cancer that makes the cells inside the host grow in a random and uncontrolled way. The speed at which the material deteriorates is adjusted to the duration of the work’s exhibition.

# IMPLEMENTATION

The Memoria project is implemented using Python and the VLC media player. The main components of the project include:

. corrupt_video(input_file, output_file_template, initial_crf=30, noise_intensity=2)


All hardware is housed in a custom case, a sculptural object in itself that was molded and 3D printed from recycled plastic filaments in collaboration with COPINCHA, a hackerspace in Havana that works with local materials and technologies.
