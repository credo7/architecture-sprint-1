# Задание #1

[Документация по Micro Frontends](https://github.com/credo7/architecture-sprint-1/tree/sprint_1/frontend/microfrontend#readme)

В качестве решения выбрал Webpack Module Federation, так как в проекте используется исключительно React.

Разделение на микрофронтенды по DDD

**Исходя из бизнес-логики, выделены следующие микрофронтенды:**
- auth – удаленный модуль для аутентификации
- photo – удаленный модуль для работы с изображениями
- profile – удаленный модуль для управления профилем пользователя
- host – основное приложение, которое динамически загружает модули auth, photo и profile

Компоненты:

**auth**:
- Login – компонент для авторизации пользователя
- Register – компонент для регистрации пользователя

**photo**:
- AddPlacePopup – компонент для добавления изображения
- ImagePopup – компонент для просмотра изображения
- PopupWithForm – компонент модального окна для сохранения
- Card – компонент карточки с изображением

**profile**:
- EditAvatarPopup – компонент для изменения аватара пользователя
- EditProfilePopup – компонент для редактирования профиля пользователя
- PopupWithForm – компонент модального окна для сохранения (используется и здесь)

**host**: // Возможно есть ризон внутренность хоста перемесить во frontend/ директорию
- App – основной компонент приложения
- Footer – подвал сайта
- Header – шапка сайта
- ProtectedRoute – компонент для защиты маршрута
- InfoTooltip – компонент информационного всплывающего окна
- Main – основной компонент, отображающий список карточек изображений
- PopupWithForm – модальное окно для сохранения (также используется здесь)

# Задание 2

[Архитектура](https://drive.google.com/file/d/1MzFmXUZOzIUDehISWOprmn09VVzpluR_/view?usp=sharing)
1. Разбиваем фронтенд на 2 микро фронта / приложения. Админская часть и клиентская часть
2. Между клиентом и фронтендом стоит API GateWay (NGINX)
3. Backend сервисы разбиты на User Service, Payment service, Support Service, Auction Service, Products/Services service, reports service, orders service
4. Также есть сервис нотификации, который забирает queue messages от producers
