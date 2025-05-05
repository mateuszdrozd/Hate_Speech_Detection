# Wykrywanie hejtu na Twitterze (Polish Twitter Hate Detection)
[Zobacz Raport]([https://github.com/mateuszdrozd/Cinema_Management_DB/blob/main/Raport%20Kino%20Bazy%20Danych.pdf](https://github.com/mateuszdrozd/Hate_Speech_Detection/blob/main/Projekt.pdf))
## Opis projektu  
Celem projektu było zbudowanie klasyfikatora NLP rozróżniającego komentarze z Twittera na **„hejt” (1)** i **„brak hejtu” (0)** w języku polskim. W zbiorze danych panowała **silna nierównowaga klas** – ok. 9× więcej neutralnych niż obraźliwych komentarzy, co stanowiło wyzwanie przy treningu modelu.  

## Dane  
Wpisy obejmują tweety zebrane z publicznie dostępnych dyskusji na **Twitterze**. Zbiór ten stanowi część polskiego benchmarku **KLEJ** (Kompleksowa Lista Ewaluacji Językowych), tweety są udostępniane w **surowej formie, z minimalnym przetwarzaniem**. Przetwarzanie dotyczy głównie sytuacji, gdy **ujawniane są informacje o osobach prywatnych**.

## Metody  
1. **Preprocessing:**  
   - Czyszczenie tekstu: usunięcie stop-words, znaków interpunkcyjnych, lowercasing.  
   - TF–IDF vectorization.  
   - Podział na zbiory treningowy (80 %) i testowy (20 %).  
2. **Ablation study:** porównanie wariantów z lematyzacją i bez lematyzacji.  
3. **Modelowanie:**  
   - Benchmarking wielu modeli (logistic regression, SVM, itp.) z GridSearchCV oraz RandomizedSearchCV.  
   - Balansowanie klas: Oversampling + back-translation, Undersampling + TomekLinks + ENN.  
4. **Ewaluacja:**  
   - Metryki: F1, precision, recall, accuracy.  
   - Macierz pomyłek, krzywe ROC, krzywe Precision-Recall Curve, Wizualizacja metryk klasyfikacyjnych w zależności od progu decyzyjnego.

## Technologie  
- Python
- pandas, numpy, scipy  
- scikit-learn, imbalanced-learn
- spaCy  
- Matplotlib, Seaborn, wordcloud
