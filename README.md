##Australia Weather MaxTemp Predictor
โปรเจคพยากรณ์อุณหภูมิสูงสุดรายวันในประเทศออสเตรเลียด้วย Machine Learning

แอปพลิเคชันนี้ถูกพัฒนาขึ้นเพื่อพยากรณ์อุณหภูมิสูงสุดของวันพรุ่งนี้ โดยวิเคราะห์จากปัจจัยทางอุตุนิยมวิทยาต่าง ๆ เช่น 
อุณหภูมิต่ำสุด, ความชื้น, ความกดอากาศ และสถานที่ เพื่อช่วยในการวางแผนกิจกรรมกลางแจ้งและการจัดการทรัพยากรที่ขึ้นอยู่กับสภาพภูมิอากาศ

##เทคโนโลยีที่ใช้ (Tech Stack)
Language: Python
Framework: Streamlit
Machine Learning: * XGBoost โมเดลหลักที่ใช้ในการพยากรณ์ LightGBM & Linear Regression: ใช้สำหรับเปรียบเทียบประสิทธิภาพ
Data Processing: Scikit-learn (Pipeline, ColumnTransformer, Standard Scaler, OneHotEncoder)
Visualization: Matplotlib, Seaborn

##วิธีการติดตั้ง


##กระบวนการพัฒนา (Methodology)
Data Cleaning & EDA: จัดการข้อมูลสูญหาย (Missing Values) ด้วยการใช้ Mean Imputer และวิเคราะห์ความสัมพันธ์ของตัวแปรผ่าน Correlation Matrix
Feature Engineering: แยกการจัดการข้อมูลตัวเลข (Numeric) และหมวดหมู่ (Categorical) อย่างเป็นระบบด้วย Machine Learning Pipeline
Model Selection: เปรียบเทียบ 3 โมเดลเพื่อหาค่า Error ที่ต่ำที่สุด
LightGBM: MAE ~0.7552
XGBoost: MAE ~0.7558 (โมเดลที่เลือกใช้หลังจากทำ Tuning)
Hyperparameter Tuning: ใช้ GridSearchCV และ 5-Fold Cross Validation เพื่อค้นหาพารามิเตอร์ที่ดีที่สุดสำหรับ XGBoost

##ผลลัพธ์ของโมเดล (Model Results)
โมเดล XGBoost ที่ผ่านการ Tuning แล้วให้ประสิทธิภาพดังนี้:
R² Score: ~0.97 (สามารถอธิบายความผันแปรของข้อมูลได้ถึง 97%)
MAE: ~0.75 °C (ความคลาดเคลื่อนเฉลี่ยเพียง 0.75 องศาเซลเซียส)

##วิธีการใช้งาน (Usage)
เลือกสถานที่ (Location): เลือกเมืองที่ต้องการพยากรณ์
กรอกข้อมูลสภาพอากาศ: ระบุอุณหภูมิต่ำสุด, ความชื้นตอนบ่าย, ความกดอากาศ และอุณหภูมิปัจจุบัน
กดปุ่ม "Predict Now": ระบบจะประมวลผลผ่าน Pipeline และแสดงผลพยากรณ์ทันที

##ข้อควรระวัง (Disclaimer)
ผลการพยากรณ์คำนวณจากแบบจำลองทางสถิติเพื่อวัตถุประสงค์ทางการศึกษาเท่านั้น

จัดทำโดย: 67160337 ธนพล แสงนวล
วิชา: Data Sci
