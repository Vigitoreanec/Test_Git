# Test_Git 

Подключение к GitHub с помощью SSH.
Все команды вводить ТОЛЬКО в git-bash

1. Создание нового ключа SSH
  ssh-keygen -t ed25519 -C "your_email@example.com"

  на все вопросы просто нажимаем Enter
  
2. Проверка наличия существующих ключей SSH
  ls -al ~/.ssh

  должны увидеть файлы id_ed25519 и id_ed25519.pub

3. Запуск ssh-agent (в фоне)
  eval "$(ssh-agent -s)"

  должна появиться строка Agent pid число 

4. Добавление в ssh-agent
  ssh-add ~/.ssh/id_ed25519

  должны увидеть Identity added и (ваша почта)

5. Копирование ОТКРЫТОГО ключа в буфер обмена
  clip < ~/.ssh/id_ed25519.pub

6. Добавление нового ключа SSH в учетную запись GitHub

  // https: //github.com/settings/keys
  Add new SSH Key
  вставляем из буфера обмена

Итог: Проверка подключения SSH
  ssh -T git@github.com

  должны увидеть Hi и имя своего аккаунта
  если спросит 
  Are you sure you want to continue connecting (yes/no/[fingerprint])? 
  надо ввести буквы yes полностью 