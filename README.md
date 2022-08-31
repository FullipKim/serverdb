# serverdb
서버디비 관련 코딩 백업

# Write results                
#for *xyxy, conf, cls in reversed(det):
#162 줄 


import time
import pymysql

    db_name = names[int(c)]
    percent = float(conf)

    conn = pymysql.connect(host="192.168.1.169",user="raspi_inae",passwd="1234",db="notbed")
    cur = conn.cursor()
    cur.execute("insert into yolov5 (date, name, conf) values(default, '''{0}''', {1:0.5f})".format(db_name, percent))
    conn.commit()
    time.sleep(1)
    conn.close()

# Password
리눅스암호: 12341234
ip : 192.168.1.180 
`

인플럭스 접속
influx -username admin -password inae0615

그라파나 
sudo systemctl daemon-reload
sudo systemctl start grafana-server
sudo service grafana-server restart

아파치
/var/www/html

http://192.168.1.180/index.html

영상처리
학습
python3 train.py --img 416 --batch 16 --epochs 50 --data /home/buzz/notbed/yolov5/data.yaml --weights yolov5s.pt

실시간카메라
python3 detect.py --device cpu --source 0 --weights /home/buzz/notbed/yolov5/runs/train/exp7/weights/best.pt

python3 detect.py --device cpu --source http://192.168.1.164:8080/?action=stream --weights /home/buzz/notbed/yolov5/runs/train/exp/weights/best.pt


python detect.py --device cpu --source 0 --weights /home/buzz/notbed/yolov5/runs/train/exp7/weights/best.pt --img 416 --conf 0.5 --save-txt
