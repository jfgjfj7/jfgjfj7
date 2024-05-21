import pandas as pd
import matplotlib.pyplot as plt

# Дані для аналізу товарної структури міжнародної торгівлі у 2022 році
trade_data = {
    'Category': ['Електроніка та електротехніка', 'Машинобудування', 'Паливно-енергетичні товари', 'Хімічна продукція', 'Продовольчі товари'],
    'Export_2022_trillion': [2.9, 2.4, 1.7, 1.4, 1.2],
    'Share_2022_percent': [11, 10, 7, 6, 5]
}

country_trade_data = {
    'Country': ['Китай', 'США', 'Німеччина', 'Японія', 'ЄС'],
    'Export_2022_trillion': [3.6, 1.8, 1.6, 0.75, 6.0],
    'Share_2022_percent': [14, 7, 6, 3, 24]
}

# Конвертуємо дані у DataFrame
df_trade = pd.DataFrame(trade_data)
df_country_trade = pd.DataFrame(country_trade_data)

# Генерація кругової діаграми для товарної структури
fig1, ax1 = plt.subplots()
ax1.pie(df_trade['Export_2022_trillion'], labels=df_trade['Category'], autopct='%1.1f%%', startangle=90)
ax1.axis('equal')  # Забезпечує колову форму діаграми
plt.title('Товарна структура міжнародної торгівлі у 2022 році')
plt.show()

# Генерація стовпчастої діаграми для географічної структури
fig2, ax2 = plt.subplots()
ax2.bar(df_country_trade['Country'], df_country_trade['Export_2022_trillion'], color=['#ff9999','#66b3ff','#99ff99','#ffcc99','#c2c2f0'])
ax2.set_xlabel('Країни')
ax2.set_ylabel('Обсяг експорту ($ трлн)')
ax2.set_title('Географічна структура міжнародної торгівлі у 2022 році')
plt.show()
