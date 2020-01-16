注意看一下 Arduino 的 digital pin 會發現，有些編號旁有 "~" 符號，這些 pin 就是可以使用 PWM pin。
Arduino PWM 的使用方式其實超簡單的，IDE code 為 analogWrite ()。

格式：analogWrite(pin, value)

參數：
pin：輸出 PWM 的 pin ，上面的例子可以是 pin 3/5/6/9/10/11
value：duty cycle，介於0~255。0 = 0%，127 = 50%，255 = 100%

analog(3,127)，就是代表由 pin 3 輸出 duty cycle 50% 的訊號。

附上一個簡單的 sketch：

int ledPin = 3; // 把 LED 接上 PWM pin3
void setup()
{
pinMode(ledPin, OUTPUT); // 設定 pin 3 為輸出
}
// 下面這個 loop 會讓 LED 燈由暗變為一半亮度，最後變成最大亮度
void loop()
{
analogWrite(ledPin, 0);  // LED 不亮
delay (1000);
analogWrite(ledPin, 127);  // LED 一半亮度
delay (1000);
analogWrite(ledPin, 255);  // LED 最大亮度
delay (1000);
}