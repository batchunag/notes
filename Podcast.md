#Steps to editing.
1) Adjust the LUFS & Maximum Amplitude.

#Steps for Editing in Audacity
> High Pass Filter
	Frequency(Hz): 70Hz
	Roll-off(dB per octave): 12dB
		For most podcasts, we can apply a high pass filter at roughly 70 Hz. Says the human voice generally starts at 80 Hz we won’t be missing any important information
> Low Pass Filter
	Frequency(Hz): 10kHz
	Roll-off(dB per octave): 12dB
		For podcasting low pass filter is generally start at 10 kHz. I have found that low pass filter will remove high-pitched noises from our podcasting microphones. Simply adding a Highpass and low pass filters to your podcast’s EQ is the best first step.

> Ref: https://streamgeeks.us/how-to-eq-a-podcast/	


1) Amplify so that Max amplitude is 0.0
	Don't allow clipping, or make it very rare!.
  Make two stereo side equal amplitude. Split the track if necessary.

2) Reduce the noise
	* Apply "Get Noise Profile" on chunk of pure noise.
	* Default parameters are:
		Noise reduction (dB): 20
		Sensivity: 6.00
		Frequency smoothing(bands): 3
		Noise: Reduce
	More: https://manual.audacityteam.org/man/noise_reduction.html

2) Equalizer
3) Condense
https://www.buzzsprout.com/blog/best-sounding-audio-for-podcast

#Peak level 
The peak level should be less than 0 dB throughout the recording. Note that MP3 encoding is an approximation of the original audio, so the peak level of an MP3 may be higher or lower than the original (usually a bit higher). It is therefore advisable to keep the peak level at no more than about -2 dB before exporting.
https://forum.audacityteam.org/viewtopic.php?t=100704

#Loudness (LUFS = Loudness Unit)
Though it is generally recognised that around -16 LUFS is a reasonable level


#Using Audacity
https://www.buzzsprout.com/blog/best-sounding-audio-for-podcast


#Normalizer 
Normalization is used to shrink the height of the sound waves without making the sound itself quieter. This will make room for adding bass boost.
 --> "Normalize maximum amplitude" to -10.0 dB
 https://www.wikihow.com/Adjust-Bass-in-Audacity


Гол ярьж байгаа хүнрүүгээ харуулаад ярих. 
Цөөн үгээр ярих
Дундаа зогссон ч болно.



#Validation
https://castfeedvalidator.com/?url=https://feeds.soundcloud.com/users/soundcloud:users:778219771/sounds.rss

#Creating RSS
https://support.google.com/podcast-publishers/answer/9476656#create_feed


Validator
https://search.google.com/devtools/podcast/preview

> Google has already indexed
	using Soundcloud RSS.

> Apple podcast: 
https://podcastsconnect.apple.com/my-podcasts/new-feed
https://help.apple.com/itc/podcasts_connect/#/itce5b9b0782


https://www.intechopen.com/books/current-trends-and-challenges-in-rfid/low-cost-solution-for-rfid-tags-in-terms-of-design-and-manufacture


#Self-hosting
https://podnews.net/article/self-hosting-podcast-tips