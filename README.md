მოდელი 1 — SimpleCNN 

პირველი მოდელი წარმოადგენს მარტივ კონვოლუციურ ნეირონულ ქსელს (CNN), სახელად SimpleCNN, რომელიც გამოიყენება FER (Facial Expression Recognition) ამოცანის გადასაჭრელად. არქიტექტურა შედგება ორი Convolutional ფენისგან, MaxPooling ფენებისგან და ორი Fully Connected ფენისგან.

არქიტექტურა:
Conv2D (1→32), kernel=3, padding=1
ReLU
MaxPooling2D (2×2)
Conv2D (32→64), kernel=3, padding=1
ReLU
MaxPooling2D (2×2)
FC1: 64×12×12 → 128
Dropout(0.5)
FC2: 128 → 7 (ემოციის კლასები)
ჰიპერპარამეტრები:
ოპტიმიზატორი: Adam
Learning rate: 0.001
Batch size: 64
Epoch-ები: 15
შედეგები:
საბოლოო Train Accuracy: 58.0%
საბოლოო Validation Accuracy: 53.1%
Train Loss (epoch 15): 1.0813
Val Loss (epoch 15): 1.2441
📌 ანალიზი:
მოდელმა აჩვენა პროგრესული გაუმჯობესება სწავლის პროცესში — ყოველ apoch-ზე ტრენინგისა და ვალიდაციის სიზუსტე თანდათან იზრდებოდა. თუმცა, საბოლოო შედეგებიდან ჩანს, რომ მოდელს დაძლეული აქვს ნაწილობრივი overfitting: ტრენინგის სიზუსტე უფრო მაღალია.
