# StarLab_UR5
[공인인증실험] 시뮬레이션과 실제 환경 사이의 오차

6차년도 실험: 5개의 물체 X 12 에피소드 = 60번의 pick 수행

# Simulation
> source ~/virtuals/shelf_env/bin/activate

> cd /home/ur-minum/minjae/TSAD/robosuite/robosuite/ShelfPick

> python ShelfStarlab.py


물체들의 위치는 XY좌표로 저장됨 (./result/pose_o5_lv1.npz). ReadPosition.ipynb 파일에서 확인 가능.

# Real Env
1. 환경 세팅하기
   
   <img src = "https://github.com/mjkang16/StarLab_UR5/blob/main/images/img1_env.jpg" width="20%">  (실제 환경 사진)
   
   - 기본 EEF 좌표 (-0.10, 0.35, 0.12) & 쿼터니언 (0.0, 0.7071, 0.7071, 0.0)
   
   - 기본 joint 값: (-1.6034, -1.5460, 2.4102, -0.8654, -4.7335, 0.0106).


   <img src = "https://github.com/mjkang16/StarLab_UR5/blob/main/images/img2_shelf.jpg" width="20%">  (서랍 위치)
   
   서랍은 위 사진과 같이 놓기.
   
   - 서랍 왼쪽 기준 EEF 좌표(-0.36, 0.43, 0.12).
  
   - 서랍 오른쪽 기준 EEF 좌표(-0.36, 0.43, 0.12).
  
   "StarLab_Test.ipynb"의 Shelf Positioning 참조

   <img src = "https://github.com/mjkang16/StarLab_UR5/blob/main/images/img3_object.jpg" width="20%">  (물체 위치)

   물체는 시뮬레이션에서 얻은 XY좌표에 놓기.
   
   - 위 사진은 (1,5) 위치에 물체를 놓은 예시.

   - 위와 같이 5개의 물체를 올려놓고, 실험을 수행하면 됨.

2. 코드 실행하기
   
   실험 코드는 "/home/ur-minun/minjae/GP3_StarLab/StarLab_Test.ipynb"에 정리해놓음. 순서대로 실행해보기.

   "GP3_StarLab" 폴더는 UR5 로봇을 조작하기 위한 코드.

   "UR_Shelf" 폴더는 행동 계획을 위한 코드.

   EEF 위치 옮기는 기본적인 코드는 "UR5.move_eef()"로, 위 코드에서 확인 가능.

   > "StarLab_Test.ipynb => Perform Test"에서 "shelf_env.do_episode()" 수행 시 업무 시작.

   > "StarLab_Test.ipynb => Perform Test"에서 "shelf_env.target_rotation_check(show_result=True)"로 하면 관측되는 point cloud를 확인할 수 있음. "Debug" 파트 확인.
