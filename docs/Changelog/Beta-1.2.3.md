This release focuses on bug fixes and stability improvements
- Fixed ReportPage fatal crash when sum of graph data equals 0
- Fixed ManualInput "Kayak" type filter to find both solo and dual kayaks
- CheckOut will now find matching NFC record with most recent startDateTime
	- This is to avoid problems if the raft is sent twice in the same day
- Sort repair history by resolution date
	- History tab in Repair Module will now compare resolution dates to detect state changes