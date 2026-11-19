# FORM

![CI](https://github.com/magdadziuzanska/FORM/actions/workflows/ci.yml/badge.svg)

FORM to aplikacja do planowania treningów siłowych, zapisywania wyników i analizowania postępów. Pozwala tworzyć plany i szablony treningowe, rejestrować serie, powtórzenia i ciężary oraz śledzić rozwój siły w czasie. Opcjonalnie umożliwia prowadzenie prostego dziennika żywieniowego i zapisywanie dat cyklu menstruacyjnego.

Pełna specyfikacja produktu: [docs/product-specification.md](docs/product-specification.md)

## Status projektu

Projekt jest w trakcie realizacji. Aktualny etap: **v0.1.0 – rdzeń aplikacji** (klasy domenowe, testy, pipeline CI/CD, tymczasowy interfejs konsolowy).

Postęp prac: [Milestones](https://github.com/magdadziuzanska/FORM/milestones)

## Technologie

- C++20
- CMake
- GoogleTest (testy jednostkowe)
- GitHub Actions (CI/CD)
- planowane: Dear ImGui i ImPlot (interfejs graficzny), JSON (zapis danych)

## Wymagania

- Windows 10/11 (x64)
- kompilator MSVC z Visual Studio 2026 lub Build Tools for Visual Studio 2026 (pakiet „Programowanie aplikacji klasycznych w języku C++”)
- CMake 3.20 lub nowszy
- Git

## Budowanie i uruchomienie

W głównym folderze projektu:

```
cmake -S . -B build
cmake --build build --config Release
.\build\Release\form.exe
```

W VS Code z rozszerzeniem CMake Tools: wybierz kit Visual Studio (amd64), kliknij **Build**, a następnie **▷** na dolnym pasku.

## Testy

Po zbudowaniu projektu:

```
ctest --test-dir build -C Release --output-on-failure
```

Testy uruchamiają się też automatycznie w GitHub Actions przy każdym pushu do gałęzi `main` i przy każdym Pull Requeście.

## Struktura projektu

```
FORM/
├── .github/workflows/   pipeline CI/CD
├── docs/                dokumentacja
├── src/                 kod aplikacji
├── tests/               testy jednostkowe
└── CMakeLists.txt       konfiguracja budowania
```

## Dokumentacja techniczna

Diagram klas i mapa koncepcji obiektowych zostaną dodane wraz z implementacją klas domenowych.

## Rejestr użycia LLM

| Plik / fragment | Narzędzie | Do czego użyto i jak zweryfikowano |
|---|---|---|
| `docs/product-specification.md` | ChatGPT | wygenerował tekst specyfikacji na podstawie moich założeń; przeczytany, zweryfikowany i poprawiony przeze mnie |
| `docs/product-specification.md`, sekcja 7 i technologie | Claude | zaproponował plan wersji i technologie; zakres i treść dostosowane przeze mnie |
| `.gitignore`, wpisy IDE | Claude | zaproponował listę wpisów; sprawdzone przeze mnie |
| `CMakeLists.txt`| Claude | wygenerowane, użyte bez zmian; przeanalizowane przeze mnie |
| `CMakeLists.txt` (sekcja testów), `tests/test_przyklad.cpp` | Claude | wygenerowane, użyte bez zmian; przeanalizowane przeze mnie |
| `.github/workflows/ci.yml` | Claude | wygenerowany; dodałam własne komentarze;|
| `README.md` | Claude | wygenerował szkielet; treść sprawdzona i dostosowana przeze mnie |