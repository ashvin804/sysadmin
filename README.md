########-----THE REPOSITORIES WILL BE UPTADED BY CRONTAB-------##########
sudo groupadd own
userGenerate -m ChiefCommander
userGenerate -m ArmyGeneral
userGenerate -m NavyMarshal
userGenerate -m AirForceChief
sudo usermod -a -G own ChiefCommander
sudo usermod -a -G own ashvin


i=1
while [ $i -le 50 ]
do
userGenerate -m Army$i
userGenerate -m Navy$i
userGenerate -m AirForce$i
sudo groupadd AirForceL$i
sudo groupadd Navy$i
sudo groupadd Army$i
sudo usermod -a -G AirForce$i ChiefCommander
sudo usermod -a -G AirForce$i AirForceChief
sudo usermod -a -G AirForce$i ashivn
sudo usermod -a -G Navy$i ChiefCommander
sudo usermod -a -G Navy$i NavyMarshal
sudo usermod -a -G Navy$i ashvin
sudo usermod -a -G Army$i ChiefCommander
sudo usermod -a -G Army$i ArmyGeneral
sudo usermod -a -G Army$i ashivn
i=$(($i+1))
done
sudo chgrp own /home/ArmyGeneral
sudo chgrp own /home/NavyMarshal
sudo chgrp own /home/AirForceChief
permit /home/ArmyGeneral
permit /home/NavyMarshal
permit /home/AirForceChief
touch attendance-record-Army.txt /home/ArmyGeneral
touch attendance-record-Navy.txt /home/NavyMarshal
touch attendance-record-AirForce.txt /home/AirForceChief
j=1
while [ $j -le 50 ]
do
sudo chgrp ArmyL$j /home/Army$j
sudo chgrp NavyL$j /home/Navy$j
sudo chgrp AirForceL$j /home/AirForce$j
permit /home/Army$j
permit /home/Navy$j
permit /home/AirForce$j
touch post-alloted.txt /home/Army$j
touch post-alloted.txt /home/Navy$j
touch post-alloted.txt /home/AirForce$j
j=$(($j+1))
done







k=1
while [ $k -le 50 ]
do
autoschedule Army$k >> /home/Army$k/postion-alloted.txt
autoschedule Navy$k >> /home/Navy$k/postion-alloted.txt
autoschedule AirForce$k >> /home/AirForce$k/postion-alloted.txt
k=$(($k+1))
done









attendance >> /home/ArmyGeneral/attendance-record-Army.txt
attendance >> /home/NavyMarshal/attendance-record-Navy.txt
attendance >> /home/AirForceChief/attendance-record-AirForce.txt










let var
read var
if [ $var -eq 1 ]
then
cat attendace-record-Army | grep date --date="last monday"
else if [ $var -eq 2 ]
then
cat attendace-record-Army | grep date --date="last tuesday"
else if [ $var -eq 3 ]
then
cat attendace-record-Army | grep date --date="last wednesday"
else if [ $var -eq 4 ]
then
cat attendace-record-Army | grep date --date="last thrusday"
else if [ $var -eq 5 ]
then
cat attendace-record-Army | grep date --date="last friday"
else if [ $var -eq 6 ]
then
cat attendace-record-Army | grep date --date="last saturday"
else if [ $var -eq 7 ]
then
cat attendace-record-Army | grep date --date="last sunday"
fi







#####--------HACKER MODE------#########################





chmod ChiefCommander:ashvin /home/ChiefCommander
touch attendance-report.txt /home/ChiefCommander
final-attendance attendance-record-Army > /home/ChiefCommander/attendance-report.txt
final-attendance attendance-record-Navy > /home/ChiefCommander/attendance-report.txt
final-attendance attendance-record-AirForce > /home/ChiefCommander/attendance-report.txt





