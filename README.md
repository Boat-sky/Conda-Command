โดยเริ่มต้นแล้ว env ที่จะเรียกใช้คือ `base`   
แต่เราก็สามารถ เอาออกได้โดยใช้
```
conda deactivate
```
และเรียกใช้โดยใช้คำสั่ง
```
conda activate base
```
ได้เหมือน env อื่นที่สร้างขึ้น   
   
ดูรายละเอียดของ conda ในเครื่อง
```
conda info
```
ดูรายชื่อ env ในเครื่อง
```
conda info --envs 
```
สร้าง env (ในที่นี้ตั้งชื่อว่า Boat และใช้ python เวอร์ชั่น 3.7
```
conda create --name Boat python==3.7
              หรือ
conda create -n Boat python=3.7
```
สร้าง env พร้อมติดตั้ง tensorflow
```
conda create -n Boat tensorflow
```   
เรียกใช้งาน env (ในที่นี้เรียกใช้ env ที่ชื่อว่า Boat)
```
conda activate Boat
```
ยกเลิกการใช้งาน env
```
conda deactivate
```
ดู package ทั้งหมดที่ติกดตั้งใน env นั้น
```
conda list --explicit
```
ติดตั้ง package
```
conda install matblotlib
```
วิธีสั่ง env ให้มี package เหมือนกับ env ที่เคยสั้งไว้
1. activate env ที่ต้องการให้คัดลอง package (ในที่นี้เรียกใช้ env ที่ชื่อว่า py3)
```
conda activate py3
```
2. บันทึกรายการ package ที่ต้องการคัดลอกเก็บไว้ใน txt ไฟล์ (ในที่นี้จะเก็บไว้ในไฟล์ Pac.txt)
```
conda list --explicit > Pac.txt
```
3. สร้าง env ใหม่โดยนำรายการที่บันทึกในไฟล์ txt มาใช้ (ในที่นี้ตั้งชื่อ env ใหม่ว่า py3_new)
```
conda create -n py3_new --file Pac.txt
```
ลบ env (ในที่นี้ลบ env ที่ชื่อว่า py3)
```
conda remove -n py3 --all
```
เพิ่ม env ernel ของ jupyter notebook
1. อาจต้องติดตั้ง upyter notebook ก่อน (สำหรับ miniconda ต้องทำ)
```
conda install -y jupyter
```
2. ติดตั้ง ipykernel
```
conda install -y ipykernel
```
3. นำ env ที่เราอยู่ไปบันทึกใน kernel พร้อมตั้งชื่อที่จะแสดงบน jupyter notebook (ในที่นี้ env ชื่อว่า tf และชื่อที่แสดงใน jupyter notebook คือ tensorflow)
```
python -m ipykernel install --user --name tf --display-name "tensorflow"
```
