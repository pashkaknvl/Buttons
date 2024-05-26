# Buttons
## Создание

Создание кнопок работает так: сами кнопки - это элементы вектора (условно назовём его `buttons`), который является элементом инлайновой клавиатуры, то есть, грубо говоря, мы сначала создаём клавиатуру, а потом заталкиваем в неё вектор с кнопками. Это сделано для того, чтобы был выбор какую кнопку нажа

#include <tgbot/tgbot.h>
#include <vector>
TgBot::InlineKeyboardMarkup::Ptr keyboard(new TgBot::InlineKeyboardMarkup);
// создали инлайновую клавиатуру
std::vector<TgBot::InlineKeyboardButton::Ptr> buttons;
// создали вектор с набором кнопок, которые будут там храниться
TgBot::InlineKeyboardButton::Ptr name_of_button(new TgBot::InlineKeyboardButton);
// создание самой кнопки
name_of_button->text = "Имя"; // как кнопка будет подписана у пользователя
name_of_button->callbackData = "data"; // то, что возвращает кнопка в бота при нажатии
buttons.push_back(name_of_button); // заталкиваем кнопки в вектор
keyboard->inlineKeyboard.push_back(buttons); // заталкиваем вектор в клавиатуру
