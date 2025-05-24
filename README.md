# Laboratorium NLP: Modele Bigramowe, Word2Vec i CBOW

**Autor:** Marcin Przybylski
**Data:** 2025 (na podstawie daty na pierwszej stronie dokumentu)

## Opis Projektu

Niniejsze laboratorium miało na celu praktyczne zapoznanie się z technikami przetwarzania języka naturalnego (NLP), ze szczególnym uwzględnieniem modeli reprezentacji słów, takich jak Word2Vec. Ćwiczenia obejmowały implementację i analizę różnych modeli przy użyciu bibliotek Gensim oraz PyTorch (architektura CBOW), przetwarzanie różnych korpusów tekstowych (polskie imiona, dialogi z serialu "The Simpsons", 4-gramy), analizę implementacji "from scratch" oraz zastosowanie technik pomocniczych, takich jak klasteryzacja K-Means i wizualizacja za pomocą PCA/t-SNE.

Wszystkie zadania programistyczne zostały wykonane w środowisku Google Colaboratory.

## Struktura Projektu / Zrealizowane Zadania

Projekt obejmował następujące zadania:

1.  **Model Bigram - Generacja Imion na Podstawie Częstości:**
    * Wczytanie polskich imion, budowa modelu bigramowego opartego na częstościach par znaków.
    * Implementacja funkcji kosztu (średni negatywny logarytm prawdopodobieństwa) i generowanie nowych imion.
2.  **Model Bigram - Generacja Imion Siecią Neuronową (PyTorch):**
    * Przygotowanie danych treningowych (bigramy znaków, kodowanie one-hot).
    * Zdefiniowanie i trening prostej sieci neuronowej (jedna warstwa liniowa) do modelowania zależności bigramowych.
    * Generowanie imion z wytrenowanego modelu neuronowego.
3.  **Analiza Dialogów "The Simpsons" z Wykorzystaniem Gensim Word2Vec:**
    * Wczytanie i wstępne przetwarzanie transkrypcji dialogów.
    * Zaawansowany preprocessing tekstu (usuwanie niepożądanych znaków, lematyzacja, usuwanie słów stopu za pomocą Spacy).
    * Tokenizacja i tworzenie bigramów słownych (`gensim.models.phrases`).
    * Trenowanie modelu Word2Vec (`gensim.models.Word2Vec`).
    * Ewaluacja semantyczna modelu (`most_similar`, `doesnt_match`).
    * Wizualizacja wektorów słów za pomocą t-SNE.
4.  **Implementacja CBOW w PyTorch:**
    * Przygotowanie danych treningowych z krótkiego korpusu tekstowego (kontekst -> słowo centralne).
    * Zdefiniowanie modelu CBOW w PyTorch (`nn.Embedding`, `nn.Linear`).
    * Trening modelu CBOW (funkcja kosztu NLLLoss, optymalizator Adam).
    * Klasteryzacja (K-Means) i wizualizacja (PCA) nauczonych embeddingów słów.
5.  **Analiza 4-gramów (Gensim Word2Vec):**
    * Pobranie i przetwarzanie pliku `raw_sentences.txt` na sekwencje słów.
    * Trening modelu Word2Vec (architektura CBOW) na przygotowanych danych.
    * Analiza podobieństwa słów (`most_similar`).
    * Wizualizacja embeddingów 4-gramowych za pomocą PCA.
6.  **Analiza Implementacji Word2Vec "From Scratch":**
    * Analiza dostarczonego kodu implementacji Word2Vec w Pythonie (NumPy) i odpowiedzi na pytania dotyczące miary podobieństwa oraz sposobu wyszukiwania najbliższych słów.
7.  **Zadanie z Notatnika Makemore: Klasteryzacja Embeddingów CBOW:**
    * Klasteryzacja (K-Means) i wizualizacja (t-SNE) wektorów słów uzyskanych z modelu CBOW (prawdopodobnie trenowanego na 4-gramach), z uwzględnieniem niezgodności rozmiarów słownika i macierzy embeddingów.
8.  **Zadanie Bonusowe: Przewidywanie Ostatniego Słowa 4-gramu (PyTorch CBOW):**
    * Przygotowanie danych treningowych (pierwsze trzy słowa 4-gramu jako kontekst, czwarte jako cel).
    * Zdefiniowanie i trening modelu CBOW w PyTorch do przewidywania ostatniego słowa.
    * Testowanie modelu i predykcja dla przykładowych kontekstów.

## Metodologia i Kluczowe Techniki

* **Modele Bigramowe:** Oparte na zliczaniu częstości oraz implementacja z użyciem sieci neuronowej (PyTorch) do generowania sekwencji znaków (imion).
* **Word2Vec (Gensim):** Wykorzystanie biblioteki Gensim do trenowania modeli Word2Vec (CBOW) na dużych korpusach tekstowych ("The Simpsons", 4-gramy) w celu nauki reprezentacji wektorowych słów i analizy semantycznej.
* **CBOW (PyTorch):** Implementacja modelu Continuous Bag of Words od podstaw w PyTorch, w tym warstwy embeddingów, agregacja kontekstu i predykcja słowa centralnego lub następnego słowa.
* **Preprocessing Tekstu:** Tokenizacja, lematyzacja, usuwanie słów stopu, tworzenie n-gramów.
* **Ewaluacja Modeli:** Funkcje kosztu (NLL, CrossEntropyLoss), analiza podobieństwa semantycznego (`most_similar`), predykcje.
* **Wizualizacja Embeddingów:** Redukcja wymiarowości (PCA, t-SNE) i wizualizacja przestrzeni wektorowych słów.
* **Klasteryzacja:** Algorytm K-Means do grupowania wektorów słów.

## Technologie i Biblioteki

* Python
* Google Colaboratory
* PyTorch
* Gensim
* Scikit-learn (PCA, K-Means, t-SNE)
* Pandas
* NumPy
* Matplotlib
* Spacy

## Podsumowanie

Laboratorium pozwoliło na praktyczne zastosowanie i zrozumienie fundamentalnych koncepcji oraz narzędzi w dziedzinie Przetwarzania Języka Naturalnego, od prostych modeli statystycznych po sieci neuronowe uczące reprezentacje słów. Eksperymenty objęły różnorodne zadania, takie jak generacja tekstu, analiza semantyczna i predykcja, na różnych zbiorach danych.
