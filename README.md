0. Go to the appropriate page to download the example duration table(copy/paste is easier with chrome browser, paste it into a google sheet), save it as 490_590_time.csv the columns are
LASTNAME	FIRSTNAME	USERNAME	GRADE	ATTEMPT NUMBER	DATE	STATUS	DURATION
(must have columns: LASTNAME FIRSTNAME	USERNAME DURATION )
1. download all assignments: From the gradebook, click on the small arrow by the "Final Exam - Time Lapse" column, and choose "Assignment File Download"
2. in Linux:
	mkdir video_ws
	cd video_ws
3. extract archive(s), make sure all video files end with .mp4 or .mov (some students submit video files without any file type)
4. in /.. path to..../video_ws:
	bash collect_video_stats>batch.csv
5. in /.. path to..../video_ws:
	python python_matching 490_590_time.csv 0 1 2 8 batch.csv>result.txt
   (format is: python_matching <path to 490_590_time.csv> <column# for last name in 490_590_time.csv> <column# for first name in 490_590_time.csv> <column# for ubid in 490_590_time.csv> <column# for Duration in 490_590_time.csv> <path to batch.csv>")
   (I used 8 instead of 7 because there is an extra "," in DATE column)

6.cat result.txt
