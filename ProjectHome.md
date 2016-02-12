Simple scrip in perl to collect data from Coban tracker devices TK-103-2.
This is first version of my aphfa aphfa perl script supporting coban tk103-2 it support only getting geo data, no alarm no command sending and no other features<br>
mysql table column: imei, session, latitude, longitude, bear, speed<br>
<br>
Config:<br>
my $Debug    = 0; #turn 0 - off/1-first level, deep level<br>
my $Coban    = 1; #turn 1 if you have coban devices (need replay for messages)<br>
my $Mysql     = 1; #trun 1 if want use mysql<br>
my $port        = 8081;		# port number for TCP only<br>
my $alarmtime = 30;		# seconds, timeout<br>
my $maxline   = 4096;		# max length of the line<br>
my $logfile   = "/tmp/trackergps.log";<br>
my $imei ="353353058353535"; #imei of tracker device<br>
# MYSQL CONFIG VARIABLES<br>
my $dbhost = "localhost";<br>
my $dbport = "3306";<br>
my $dbname = "somedbname";<br>
my $dbtable = "sometablename";<br>
my $dbuser = "username";<br>
my $dbpw = "somepassword";<br>
<br>
##Need to do:<br>
# Separate fork for incoming connection - 1 device 1 fork/thread?<br>
# Thread in every fork for mysql handling ?<br>
# Add more cases (if signal low, if alarm messages etc, if some error)<br>
# Add error and message tracking (better breake point)?<br>
# Add multi imei support<br>
# Making script worki in deamon mode<br>
<br>