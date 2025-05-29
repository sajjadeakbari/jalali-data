

<!-- Badges will be added here after initial PyPI release and CI setup -->
<!-- 
[![PyPI version](https://badge.fury.io/py/jalali-data.svg)](https://badge.fury.io/py/jalali-data)
[![CI - Test](https://github.com/sajjadeakbari/jalali-data/actions/workflows/test.yml/badge.svg)](https://github.com/sajjadeakbari/jalali-data/actions/workflows/test.yml)
[![Coverage Status](https://coveralls.io/repos/github/sajjadeakbari/jalali-data/badge.svg?branch=main)](https://coveralls.io/github/sajjadeakbari/jalali-data?branch=main)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python Versions](https://img.shields.io/pypi/pyversions/jalali-data.svg)](https://pypi.org/project/jalali-data/)
-->

A comprehensive Python library for working with Jalali (Shamsi), Hijri (Islamic), and Gregorian calendars. `jalali-data` focuses on **high precision** by implementing robust astronomical and algorithmic rules (e.g., for complex Hijri leap year calculations) and aims for **long-term support** by covering a wide historical date range and committing to ongoing maintenance and updates.

**برای مشاهده توضیحات کامل به زبان فارسی، لطفاً به فایل [README.fa.md](README.fa.md) مراجعه کنید.**

`jalali-data` is designed to be a reliable and accurate tool for developers and researchers needing to perform date conversions, calculations, and formatting across different calendar systems, with a special focus on Jalali and Hijri calendars commonly used in Persian-speaking countries and the Islamic world.

## Key Features (Planned)

1.  **Accurate Conversions:** Precise algorithms for converting dates between Jalali, Hijri, and Gregorian calendars, ensuring correctness based on established calendrical rules.
2.  **Leap Year Calculation:** Automatic and accurate leap year determination for all supported calendars, including various observational and algorithmic approaches for Hijri.
3.  **Wide Date Range Support:** Designed to handle a broad spectrum of years, facilitating both historical research and future date projections.
4.  **Multi-language Support (i18n/L10n):**
    *   Date formatting in Persian, Arabic, and English.
    *   Localized names for months and days of the week.
    *   Full Right-to-Left (RTL) support for Persian and Arabic outputs.
5.  **Integration & Compatibility:**
    *   Seamless conversion to and from Python's standard `datetime` objects.
    *   Planned support for easy use with Pandas DataFrames and Series.
6.  **Advanced Utilities:**
    *   Calculation of Islamic religious occasions (with configurable accuracy).
    *   Management of official holidays (initially for Iran, extensible to other regions).
    *   Accurate age calculation based on different calendars.
    *   Tools for handling significant historical dates.
7.  **Robust Validation & Error Handling:**
    *   Strict validation of input dates (e.g., "31 Esfand 1400" vs. "30 Bahman 1402").
    *   Clear, informative, and custom exceptions for easier debugging.

## Installation

Once published, you can install `jalali-data` via pip:

```bash
pip install jalali-data
```

To use it locally for development or to contribute:

1.  Clone the repository:
   
    ```bash
    git clone https://github.com/sajjadeakbari/jalali-data.git
    cd jalali-data
    ```
    
3.  Install in editable mode with all development dependencies (for testing, linting, docs):
   
    ```bash
    pip install -e ".[dev,test,docs]"
    ```
    If you only need the core library for local use:
    
    ```bash
    pip install -e .
    ```

## Quick Start

```python
# Example usage will be available once core functionalities are implemented.
# Stay tuned!

# --- Hypothetical Example ---
# from datetime import date
# from jalali_data import JalaliDate, GregorianDate

# # Get today's date in Jalali
# today_jalali = JalaliDate.today()
# print(f"امروز (شمسی): {today_jalali.strftime('%A %d %B %Y', locale='fa')}") 
# # Expected: امروز (شمسی): یکشنبه ۲۵ فروردین ۱۴۰۳ (if today is 2024-04-14)

# # Convert from Gregorian
# g_date = GregorianDate(2023, 3, 21) # Nowruz 1402
# j_date = JalaliDate.from_gregorian(g_date.year, g_date.month, g_date.day)
# print(f"Gregorian {g_date} is Jalali {j_date}")
# # Expected: Gregorian 2023-03-21 is Jalali 1402-01-01

# # Add 1 month and 10 days to a Jalali date
# new_j_date = j_date.add(months=1, days=10)
# print(f"{j_date} + 1 month and 10 days = {new_j_date}")
# # Expected: 1402-01-01 + 1 month and 10 days = 1402-02-11
```

## Documentation

Comprehensive documentation is planned and will be available at:
[sajjadakbari.ir/jalali-data.html](https://sajjadakbari.ir/jalali-data.html)

(We may also host documentation on services like ReadTheDocs or GitHub Pages in the future.)

## Contributing

We highly welcome contributions! Whether it's reporting a bug, proposing a new feature, or submitting a pull request, your help is appreciated.

Please read our [**CONTRIBUTING.md**](CONTRIBUTING.md) for guidelines on:
*   Reporting issues (you can go directly to our [Issue Tracker](https://github.com/sajjadeakbari/jalali-data/issues)).
*   Submitting pull requests.
*   Coding standards and development setup.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for full details.

---

*Developed by Sajjad Akbari ([@sajjadeakbari on GitHub](https://github.com/sajjadeakbari))*
