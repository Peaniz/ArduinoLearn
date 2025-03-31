# LED Matrix

const int ledCount = 8;
const int ledPin[ledCount] = {13, 12, 11, 10, 9, 8, 7, 6};

const int button1 = 4;  // Chân kết nối Button 1
const int button2 = 5;  // Chân kết nối Button 2

void setup() {
    for (int i = 0; i < ledCount; i++) {
        pinMode(ledPin[i], OUTPUT);
    }
    pinMode(button1, INPUT_PULLUP);  // Kích hoạt điện trở kéo lên nội bộ
    pinMode(button2, INPUT_PULLUP);
}

void loop() {
    
    if (digitalRead(button1) == LOW) {
        effectA();  // Gọi hiệu ứng A khi nhấn nút 1
    } else if (digitalRead(button2) == LOW) {
        effectB();  // Gọi hiệu ứng B khi nhấn nút 2
    }
}

// Hiệu ứng A: 3 LED chạy nối đuôi xoay vòng
void effectA() {
    for (int i = 0; i < ledCount; i++) {
        allLedOff();
        for (int j = 0; j < 3; j++) {
            int index = (i + j) % ledCount;  // Xoay vòng chỉ số LED
            digitalWrite(ledPin[index], HIGH);
        }
        delay(200);
    }
}

// Hiệu ứng B: Sáng từ 1 đến 8 LED và giảm dần
void effectB() {
    // Sáng dần từ 1 đến 8 LED
    for (int i = 0; i < ledCount; i++) {
        digitalWrite(ledPin[i], HIGH);
        delay(200);
    }
    delay(500);  // Giữ trạng thái sáng tất cả LED

    // Giảm dần từ 8 về 1 LED
    for (int i = ledCount - 1; i >= 0; i--) {
        digitalWrite(ledPin[i], LOW);
        delay(200);
    }
}

// Hàm tắt tất cả LED
void allLedOff() {
    for (int i = 0; i < ledCount; i++) {
        digitalWrite(ledPin[i], LOW);
    }
}