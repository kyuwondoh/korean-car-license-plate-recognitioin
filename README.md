# 🚗 Korean License Plate Recognition (한국 차량 번호판 인식 시스템)
**한국 차량 번호판 인식 시스템**  
**Korean License Plate Recognition System**

🔗 **Try it on Hugging Face:** [https://huggingface.co/spaces/kyuwondoh/korean_car_license_plate_recognition]  

👤 **Developed by:** 도규원 (Do Kyuwon)  

---

## 📌 소개 | Introduction
이 웹 애플리케이션은 **한국 차량 번호판을 자동으로 인식하고 한글까지 정확히 추출하는 AI 시스템**입니다.  
This web application is an **AI system that automatically recognizes Korean vehicle license plates and accurately extracts Hangul characters**.

단순한 문자 인식(OCR)이 아니라, ➡️ **번호판 검출 → 문자 검출 → 한글 변환 → 지역명 교정**  
➡️ **Plate Detection → Character Recognition → Hangul Conversion → Region Correction**

까지 한 번에 수행하는 **엔드 투 엔드(end-to-end)** 구조로 설계되었습니다.  
 
It’s not just a simple OCR system, but rather an integrated process of  
It is designed as a complete **end-to-end** system.

---

## ⚙️ 주요 기능 | Key Features

✅ **자동 번호판 검출 (YOLO 기반)**  
✅ **Automatic License Plate Detection (YOLO-based)**  
- 차량 이미지 속 번호판을 정확하게 탐지하고 겹치는 후보는 자동 제거합니다.  
- Accurately detects license plates in vehicle images and removes overlapping candidates automatically.

✅ **한글/숫자 문자 인식 (CTM 기반 2-Stage Ensemble)**  
✅ **Hangul/Numeric Character Recognition (CTM-based 2-Stage Ensemble)**  
- 문자 기울기와 배치를 고려해 회전 보정(adaptive rotation)을 수행하고,  
- Performs adaptive rotation correction considering character tilt and layout,  
- 두 개의 YOLO 텍스트 모델을 활용해 더 높은 인식률을 달성합니다.  
- Uses two YOLO text models to achieve higher recognition accuracy.

✅ **한국어 완전 지원**  
✅ **Full Korean Language Support**  
- 한글 폰트를 내장해 결과 이미지 위에 한글 텍스트가 깨지지 않고 표시됩니다.  
- Embedded Korean fonts ensure that Hangul text is displayed correctly on images.  

✅ **다중 번호판 처리 및 슬라이드 뷰 지원**  
✅ **Multi-plate Processing and Slide View Support**  
- 한 이미지 내 여러 대의 차량 번호판을 동시에 인식합니다.  
- Recognizes multiple vehicle plates within a single image.  
- 결과 이미지를 슬라이드로 쉽게 확인할 수 있습니다.  
- Easily review results in a convenient slideshow view.

---

## 🧠 기술 스택 | Tech Stack
- **YOLOv8 (Ultralytics)** — 번호판 및 문자 검출 | License plate and character detection  
- **OpenCV + Pillow** — 이미지 전처리 및 시각화 | Image preprocessing and visualization  
- **Gradio** — 웹 인터페이스 구성 | Interactive web interface  
- **Scikit-learn (LinearRegression, KMeans)** — 번호판 기울기 및 줄 배치 분석 | Plate tilt and line layout analysis  
- **Python 3.10+**

---

## 💡 사용 방법 | How to Use
1. 이미지를 업로드하거나 복사해 붙여넣습니다.  
   Upload or paste a vehicle image.  
2. “🚀 인식 실행” 버튼을 클릭합니다.  
   Click the “🚀 Run Recognition” button.  
3. 번호판이 자동 인식되고, 한글 텍스트가 박스 위에 표시됩니다.  
   The plate will be automatically recognized, and Hangul text will appear above it.  
4. “디버그 보기” 옵션을 통해 문자 검출 및 회전 과정을 자세히 볼 수 있습니다.  
   Enable “Show Debug View” to visualize character detection and rotation correction.

---

## 🌏 활용 예시 | Example Use Cases
- 차량 출입 통제 시스템 | Vehicle access control system  
- 주차장 자동 요금 정산 | Automated parking fee system  
- 교통 데이터 수집 / AI 연구 | Traffic data collection / AI research  
- OCR 모델 비교 / 학습용 데이터 검증 | OCR model evaluation / dataset validation

---

## 🧩 특징 요약 | Summary of Features
| 기능 (Feature) | 설명 (Description) |
|----------------|--------------------|
| 다중 번호판 (Multi-plate) | 한 이미지에서 여러 차량 번호판 인식 | Recognizes multiple license plates in one image |
| 한글 지원 (Korean Support) | 폰트 및 지역명 자동 교정 | Built-in font and region name correction |
| 속도 최적화 (Speed Optimization) | 자동 리사이즈, 2단계 인식 생략 로직 | Auto resize & adaptive two-pass logic |
| 실시간 디버그 (Real-time Debug) | 인식 과정 시각화 및 Confidence 표시 | Visual debugging with confidence metrics |

---

## 📸 시연 예시 | Demo Example
![Demo Image](https://raw.githubusercontent.com/kyuwondoh/korean-car-license-plate-recognition/hg.jpg)

---

## 💬 개발자 노트 | Developer’s Note
> “한글 번호판 인식은 단순한 OCR이 아닙니다.  
> Korean license plate recognition is more than simple OCR.  
> 차량, 각도, 조명, 글자 배치 등 다양한 조건을 고려해야 하기 때문에,  
> It must handle various conditions such as vehicle angle, lighting, and character layout.  
> 모델의 정밀도와 전처리 로직의 균형이 매우 중요합니다.  
> Balancing model precision and preprocessing is crucial.  
> 본 프로젝트는 실제 환경에서도 높은 정확도를 달성하기 위해  
> This project aims to achieve high accuracy in real-world conditions  
> YOLO 기반 검출과 Adaptive Rotation 알고리즘을 결합하였습니다.”  
> by combining YOLO-based detection with an Adaptive Rotation algorithm.

---
