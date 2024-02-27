Этот проект предоставляет класс на языке Python, DBManager, который позволяет управлять базой данных PostgreSQL. Он включает методы для создания таблиц, сохранения данных в базу данных и извлечения данных из базы данных. Проект также включает вспомогательную функцию get_data(), которая получает данные о работодателях и вакансиях с использованием API HeadHunter.

Предварительные требования
Перед запуском этого кода убедитесь, что у вас есть следующие предварительные требования:
Установлена библиотека psycopg2 (pip install psycopg2)
Установлена библиотека dotenv (pip install python-dotenv)
Все необходимые зависимости можно установить из файла requirements.txt (pip install -r requirements.txt)
Вам также потребуется настроить необходимые переменные окружения для подключения к базе данных. Создайте файл .env в корневом каталоге проекта и добавьте следующие переменные:

db_name=имя_вашей_базы_данных
db_host=хост_вашей_базы_данных
db_user=пользователь_вашей_базы_данных
db_password=пароль_вашей_базы_данных
Использование
Импортируйте класс DBManager из модуля class_dbmanager и функцию get_data() из модуля utils:

from data.class_dbmanager import DBManager
from data.utils import get_data
Создайте экземпляр класса DBManager:

db_manager = DBManager()
Вызовите метод create_tables() на объекте db_manager, чтобы создать необходимые таблицы в базе данных:

db_manager.create_tables()
Используйте функцию get_data() для получения данных о работодателях и вакансиях:

employers_data, vacancies_data = get_data()
Сохраните данные о работодателях и вакансиях в базе данных с помощью методов save_employers_to_db() и save_vacancies_to_db():

db_manager.save_employers_to_db(employers_data)
db_manager.save_vacancies_to_db(vacancies_data)
Используйте различные методы объекта db_manager для извлечения и работы с данными в базе данных:

db_manager.get_companies_and_vacancies_count()
db_manager.get_avg_salary()
db_manager.get_all_vacancies()
db_manager.get_vacancies_with_higher_salary()
db_manager.get_vacancies_with_keyword()
