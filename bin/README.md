Virus Total
-----------

otp-qt.exe is at:
https://www.virustotal.com/gui/file-analysis/NGEzYzQzODhlY2ZiMWMyNWMyYTU2MmRkYjQ2YTY3MmM6MTc4ODQ0MjYxNg==

This is funny, because only Microsoft thinks it is a Trojan.  This is freshly written and compiled C++ code for Qt.  It is pretty short,
so it is easy to review.

python version, otp.exe is at:
https://www.virustotal.com/gui/file-analysis/YmFlYmUwOThiODdkYzc3MGMwZjE3ZDlmMDc1ZTI3MjM6MTc4ODQ0MjkwMQ==

This one looks scarier, because Elastic, SecureAge and Zillya flagged it as suspicious or malicious.  This is often the case with Python
programs that use the pyinstaller, so it seems their accusation is somewhat simplistic.  If you are realy worried, run the build step
yourself, or just run the [otp.py](otp.py) python version using the wrapper provided [otp.cmd](otp.cmd)
