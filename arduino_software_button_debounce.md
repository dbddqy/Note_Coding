# arduino software_button_debounce

简单的debounce函数:

```cpp
bool readButtonDebounce(bool lastState, int buttonPin) {
  bool currentState = digitalRead(buttonPin);
  if (lastState != currentState) {
    delay(10); // 当按钮状态与上次不一样时，隔10ms再观察一次
    currentState = digitalRead(buttonPin);
  }
  return currentState;
}
```

使用时:

```cpp
if (currentState == HIGH && lastState == LOW) {
    lastState = HIGH;
    // 这里做按钮按下时的事情
  }
if (currentState == LOW && lastState == HIGH) {
    lastState = LOW;
}
```
