# DMARC
ColdFusion scripting to populate a database with DMARC reporting information and display data.

# Back work
Use fetchmail to retrieve messages. CFIMAP does not actually seem to retrieve file attachments. Since I don't get that many reports, I set the polling interval to 14400 seconds (every 4 hours). Don't forget to set the correct IMAP folder if you're also collecting abuse reports in that mailbox.

There is a secondary bash script named "getxml.sh" which will extract the XML messages. (The script was mainly taken from https://gist.github.com/iiikhsan/6aecaa866ed4aa4ed621.) It currently only checks for .zip and .gz archives as those are the only two types that I've gotten in several years of report collecting. This script assumes that new messages are being placed in ~/Maildir/new (fetchmail hands the messages off to procmail for local delivery). It also assumes the existence of the following directories:

~/Maildir/process
~/Maildir/process/archive
~/Maildir/process/extract
~/Maildir/process/landing
~/Maildir/process/store

# License
This project is licensed under the GNU Affero General Public License - see the [LICENSE](https://github.com/MickLC/DMARC/blob/master/LICENSE) file for details
