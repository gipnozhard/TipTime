# TipTime

## 2. Запуск проекта

Ознакомьтесь с калькулятором чаевых в Google: https://www.google.com/search ?q = чаевые + калькулятор

![image](https://github.com/gipnozhard/TipTime/assets/71705375/ce9a0b11-0392-45ba-9bcb-ef27b539bbe3)

На этом пути вы создадите простую версию калькулятора чаевых в виде приложения для Android.

Разработчики часто работают таким образом — готовят простую версию приложения, которая частично функционирует (даже если она выглядит не очень хорошо), а затем делают ее полностью функциональной и визуально отшлифованной позже.

К концу этой кодовой таблицы ваше приложение tip calculator будет выглядеть следующим образом:

![image](https://github.com/gipnozhard/TipTime/assets/71705375/44036457-f517-40c7-84ce-af8c15e67ce7)


Вы будете использовать эти элементы пользовательского интерфейса, предоставляемые Android:

 * EditText - для ввода и редактирования текста

 * TextView - для отображения текста, такого как сервисный вопрос и сумма чаевых
 
 * RadioButton - выбираемый переключатель для каждого варианта подсказки

 * RadioGroup - группировать параметры переключателей

 * Switch - переключатель включения / выключения для выбора, округлять подсказку или нет

### Создайте пустой проект Activity

 1. Для начала создайте новый проект Kotlin в Android Studio, используя Пустой шаблон Activity.

 2. Назовите приложение "Tip Time" с минимальным уровнем API 19 (KitKat). Имя пакета - com.example.tiptime.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/1446d6a6-7688-4159-8462-56c11f4ecf88)

 3. Нажмите "Готово", чтобы создать приложение.

## 3. Читать и понимать XML

Вместо использования Редактора макетов, с которым вы уже знакомы, вы создадите макет своего приложения, изменив XML, описывающий пользовательский интерфейс. Изучение того, как понимать и изменять макеты пользовательского интерфейса с помощью XML, будет важно для вас как разработчика Android.

Вы будете просматривать и редактировать XML-файл, который определяет макет пользовательского интерфейса для этого приложения. XML расшифровывается как eXtensible Markup Language, который представляет собой способ описания данных с использованием текстового документа. Поскольку XML является расширяемым и очень гибким, он используется для многих разных целей, включая определение макета пользовательского интерфейса приложений Android. Возможно, вы помните из предыдущих codelabs, что другие ресурсы, такие как строки для вашего приложения, также определены в XML-файле с именем strings.xml.

Пользовательский интерфейс приложения для Android построен как иерархия компонентов (виджетов) и экранных макетов этих компонентов. Обратите внимание, что эти макеты сами являются компонентами пользовательского интерфейса.

Вы описываете иерархию представления элементов пользовательского интерфейса на экране. Например, ConstraintLayout (родительский элемент) может содержать Buttons, TextViews ImageViews или другие представления (дочерние элементы). Помните, ConstraintLayout это подкласс ViewGroup. Он позволяет гибко позиционировать или изменять размер дочерних представлений.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/1fcc646e-e8c9-4f3b-9895-698c9f3ef733)

Иерархия содержимого приложения для Android

------------------------------------------------------------------

ПРИМЕЧАНИЕ: Видимая иерархия пользовательского интерфейса основана на сдерживании, т.Е. Внутри одного компонента находится один или несколько компонентов. Это не связано с иерархией классов и подклассов, о которой вы узнали ранее. Иногда используются термины родительский и дочерний, но в данном контексте речь идет о родительских представлениях (viewgroups), содержащих дочерние представления, которые, в свою очередь, могут содержать дочерние представления.

------------------------------------------------------------------

![image](https://github.com/gipnozhard/TipTime/assets/71705375/eb517593-cfdb-4003-8d8c-ea494034e62c)

Каждый элемент пользовательского интерфейса представлен элементом XML в XML-файле. Каждый элемент начинается и заканчивается тегом, и каждый тег начинается с < и заканчивается на >. Точно так же, как вы можете устанавливать атрибуты для элементов пользовательского интерфейса с помощью редактора макетов (design), XML-элементы тоже могут иметь атрибуты. Упрощенно XML для приведенных выше элементов пользовательского интерфейса может быть примерно таким:

![image](https://github.com/gipnozhard/TipTime/assets/71705375/c7c05c6a-d1ad-4bf2-803c-f1d3a4e68ec9)

![image](https://github.com/gipnozhard/TipTime/assets/71705375/bf91c0de-af43-4a35-86d1-86c6e911abf9)

Давайте рассмотрим реальный пример.

 1. Открыть activity_main.xml (разрешение > макет > activity_main.xml).

 2. Вы могли заметить, что приложение показывает a TextView с надписью "Hello World!" внутри a ConstraintLayout, как вы видели в предыдущих проектах, созданных на основе этого шаблона.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/b4aff30f-29cb-4c24-b135-a4e4c17aa7c1)

 3. Найдите параметры для представлений кода, разделения и дизайна в правом верхнем углу редактора макетов.

 4. Выберите вид кода.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/bf0ae23a-19cf-4742-b802-1f2dc4cba67e)

Вот как выглядит XML в activity_main.xml:

![image](https://github.com/gipnozhard/TipTime/assets/71705375/f7ebb1b5-fa2f-466c-b0bc-3eca92cf3a82)

Здесь происходит намного больше, чем в упрощенном примере, но Android Studio делает некоторые вещи, помогающие сделать XML более читаемым, точно так же, как это происходит с вашим кодом Kotlin.

 5. Обратите внимание на отступ. Android Studio делает это автоматически, чтобы показать вам иерархию элементов. TextView Имеет отступ, потому что он содержится в ConstraintLayout. ConstraintLayout Является родительским, а TextView - дочерним. Атрибуты для каждого элемента имеют отступ, чтобы показать, что они являются частью этого элемента.

 6. Обратите внимание на цветовую маркировку — некоторые элементы выделены синим, некоторые -зеленым и так далее. Похожие части файла выделены тем же цветом, чтобы помочь вам их сопоставить. В частности, обратите внимание, что Android Studio рисует начало и конец тегов элементов одним и тем же цветом. (Примечание: цвета, используемые в codelab, могут не совпадать с тем, что вы видите в Android Studio.)

### XML-теги, элементы и атрибуты

Вот упрощенная версия TextView элемента, чтобы вы могли ознакомиться с некоторыми важными частями:

![image](https://github.com/gipnozhard/TipTime/assets/71705375/fa6d3dd7-9a30-407a-8809-872ed3d437b9)

Строка с <TextView является началом тега, а строка с /> - концом тега. Строка с android:text="Hello World!" является атрибутом тега. Он представляет собой текст, который будет отображаться с помощью TextView. Эти 3 строки являются широко используемым сокращением, называемым тегом с пустым элементом. Это означало бы то же самое, если бы вы написали это с отдельным начальным тегом и конечным тегом, вот так:

![image](https://github.com/gipnozhard/TipTime/assets/71705375/afed0e41-d325-42a2-8c73-0e8cf8b92232)

Также часто с тегом с пустым элементом записывают его на как можно меньшем количестве строк и объединяют конец тега со строкой перед ним. Таким образом, вы можете увидеть тег с пустым элементом в двух строках (или даже в одной строке, если у него нет атрибутов):

![image](https://github.com/gipnozhard/TipTime/assets/71705375/ca6d9fd7-320d-4d00-8c57-76d06b722bf6)

ConstraintLayoutЭлемент записывается с отдельными начальными и конечными тегами, потому что он должен иметь возможность содержать внутри себя другие элементы. Вот упрощенная версия ConstraintLayout элемента с TextView элементом внутри него:

![image](https://github.com/gipnozhard/TipTime/assets/71705375/9ece606a-c05d-4377-ac7b-51dab6c6f223)

Если бы вы хотели добавить еще один View дочерний элемент ConstraintLayout, например, a Button под TextView TextView, он должен был бы располагаться после конца /> тега ConstraintLayout и перед конечным тегом the, как это:

![image](https://github.com/gipnozhard/TipTime/assets/71705375/66ecffe1-a074-44e6-abf7-1a363797ae85)

### Подробнее о XML для макетов

 1. Посмотрите на тег для ConstraintLayout и обратите внимание, что он говорит androidx.constraintlayout.widget.ConstraintLayout вместо просто ConstraintLayout как TextView. Это потому, что ConstraintLayout является частью Android Jetpack, который содержит библиотеки кода, предлагающие дополнительные функциональные возможности поверх основной платформы Android. Jetpack обладает полезной функциональностью, которой вы можете воспользоваться, чтобы упростить создание приложений. Вы узнаете, что этот компонент пользовательского интерфейса является частью Jetpack, потому что он начинается с "androidx".

 2. Возможно, вы заметили строки, которые начинаются с xmlns:, за которыми следуют android, app и tools.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/427d51bc-022e-4f48-9d9c-1b4be5a086cb)

xmlns Означает пространство имен XML, и каждая строка определяет схему или словарь атрибутов, связанных с этими словами. android:Пространство имен, например, помечает атрибуты, определенные системой Android. Все атрибуты в XML-макете начинаются с одного из этих пространств имен.

 3. Пробелы между XML-элементами не меняют значения для компьютера, но они могут помочь сделать XML более удобным для чтения людям.

Android Studio автоматически добавит некоторые пробелы и отступы для удобства чтения. Позже вы узнаете, как заставить Android Studio убедиться, что ваш XML соответствует соглашениям о стиле кодирования.

 4. Вы можете добавлять комментарии к XML, точно так же, как вы бы делали с кодом Kotlin. Начинайте <!-- и заканчивайте на -->.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/eb2990cb-2537-477a-9ffc-96994579499e)

 5. Обратите внимание на первую строку файла:

Это указывает на то, что файл является XML-файлом, но не каждый XML-файл включает это.

---------------------------------------------------------------

Примечание: Если возникла проблема с XML для вашего приложения, Android Studio пометит проблему, выделив текст красным цветом. Если вы наведете курсор мыши на красный текст, Android Studio покажет дополнительную информацию о проблеме. Если проблема не очевидна, посмотрите на отступы и цветовую кодировку, и они могут дать вам ключ к пониманию того, что не так.

---------------------------------------------------------------

 ## 4. Создайте макет в формате XML

1. Все еще в activity_main.xml режиме, переключитесь в режим разделения экрана, чтобы увидеть XML рядом с редактором дизайна. Редактор дизайна позволяет вам предварительно просмотреть макет вашего пользовательского интерфейса.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/5f77dfd0-0f29-4755-85ac-b6f763e53dd2)

 2. Какой вид вы используете, зависит от личных предпочтений, но для этой кодовой лаборатории используйте вид "Разделить", чтобы вы могли видеть как редактируемый вами XML, так и изменения, внесенные этими правками в редакторе дизайна.

 3. Попробуйте щелкнуть по разным строкам, одной под ConstraintLayout, а затем еще одной под TextView, и обратите внимание, что соответствующий вид выбран в редакторе дизайна. Обратное тоже работает — например, если вы нажмете на TextView в редакторе дизайна, соответствующий XML будет выделен.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/4d62fca0-8f15-4831-9ede-6432eb265b7c)

 ### Удалить текстовое представление

 1. TextView Сейчас вам не нужен, поэтому удалите его. Обязательно удалите все, начиная с <TextView и заканчивая завершением />.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/80250ced-99d3-480d-b233-7f7405b5969c)

Все, что осталось в файле, - это ConstraintLayout:

![image](https://github.com/gipnozhard/TipTime/assets/71705375/650db271-dc5c-4f28-9a80-cf5e21097550)

 2. Добавьте 16dp отступов к ConstraintLayout, чтобы пользовательский интерфейс не был перегружен краем экрана.

Заполнение похоже на поля, но оно добавляет пространство внутри ConstraintLayout вместо добавления пространства снаружи.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/6bac5281-4c32-4a15-81dc-bd4b4160e38e)

-------------------------------------------------------------------

Примечание: Некоторые фрагменты кода в этой кодовой лаборатории не будут показывать все для краткости. Код, который не меняется или не актуален для текущего шага будут представлены с многоточием (3 последовательных точек ...), так что вы можете сосредоточиться на наиболее важные части кода.

-------------------------------------------------------------------

### Добавить текстовое поле "стоимость услуги"

На этом шаге вы добавите элемент пользовательского интерфейса, который позволит пользователю вводить стоимость обслуживания в приложение. Вы будете использовать EditText элемент, который позволяет пользователю вводить или изменять текст в приложении.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/4d8ddd6b-2cbc-4360-a405-7e1814050213)

 1. Ознакомьтесь с EditText документацией и изучите образец XML.

 2. Найдите пустое пространство между открывающим и закрывающим тегами ConstraintLayout.

 3. Скопируйте и вставьте XML-файл из документации в это пространство вашего макета в Android Studio.

Ваш файл макета должен выглядеть следующим образом:

![image](https://github.com/gipnozhard/TipTime/assets/71705375/28df788d-db00-4015-98c4-807671d561a0)

Возможно, вы еще не все поняли, но это будет объяснено на следующих шагах.

 4. Примечание EditText подчеркнуто красным цветом.

 5. Наведите на него указатель, и вы увидите ошибку "просмотр не ограничен", которая должна выглядеть знакомой по более ранним codelabs. Напомним, что дочерним элементам a ConstraintLayout нужны ограничения, чтобы макет знал, как их расположить.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/66de08bb-561c-4c86-af22-0e7bd5c3689a)

 6. Добавьте эти ограничения в EditText, чтобы привязать его к верхнему левому углу родительского файла.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/9ed22240-a26e-412e-bbfe-fedc4ca31dc6)

Если вы пишете на английском или другом языке, который пишется слева направо (LTR), начальным краем является левый. Но некоторые языки, такие как арабский, пишутся справа налево (RTL), поэтому начальный край - правый. Вот почему ограничение использует "start", чтобы оно могло работать как с LTR, так и с RTL языками. Аналогично, ограничения используют "end" вместо right .

--------------------------------------------------------------

Примечание: Название ограничений следует за формой, layout_constraint<Source>_to<Target>Of где <Source> указано текущее представление. <Target> относится к краю целевого представления, к которому привязан текущий вид, либо родительский контейнер, либо другое представление.

--------------------------------------------------------------

С добавлением новых ограничений EditText элемент будет выглядеть следующим образом:

![image](https://github.com/gipnozhard/TipTime/assets/71705375/c7343fe4-f5a0-4b1c-9218-bf6c3bc7f797)

### Просмотрите атрибуты EditText

Дважды проверьте все EditText атрибуты, которые вы вставили, чтобы убедиться, что это работает для того, как это будет использоваться в вашем приложении.

 1. Найдите id атрибут, для которого установлено значение @+id/plain_text_input.

 2. Измените id атрибут на более подходящее имя, @+id/cost_of_service.

---------------------------------------------------------------

Примечание: Идентификатор ресурса - это уникальное имя ресурса для элемента. Когда вы добавляете View тот или иной ресурс с помощью редактора макетов, Android Studio автоматически присваивает им идентификаторы ресурсов. Когда вы вручную вводите XML-файл, вам необходимо явно указать идентификатор ресурса самостоятельно. Новые идентификаторы представлений в вашем XML-файле должны быть определены с префиксом @+id, который указывает Android Studio добавить этот идентификатор в качестве нового идентификатора ресурса.

Выберите описательные имена для ресурсов, чтобы вы знали, к чему они относятся, но все они должны быть написаны строчными буквами, а несколько слов следует разделять знаком подчеркивания.

Когда вы ссылаетесь на идентификаторы ресурсов в коде вашего приложения, используйте R.<type>.<name>; например, R.string.roll. Для View идентификаторов <type> используется id, например, R.id.button.

---------------------------------------------------------------

 3. Посмотрите на layout_height атрибут. Для него установлено значениеwrap_content, что означает, что высота будет такой же, как и содержимое внутри него. Это нормально, потому что там будет только 1 строка текста.

 4. Посмотрите на layout_width атрибут. Для него установлено значение match_parent, но вы не можете установить его match_parent для дочернего элемента ConstraintLayout. Кроме того, текстовое поле не обязательно должно быть таким широким. Установите для него фиксированную ширину 160dp, которой должно быть достаточно для ввода пользователем стоимости обслуживания.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/32adca4b-c708-48c2-84da-62ef58358011)

 5. Обратите внимание на inputType атрибут — это что-то новое. Значение атрибута равно "text", что означает, что пользователь может вводить любые текстовые символы в поле на экране (алфавитные символы, условные обозначения и т.д.)

![image](https://github.com/gipnozhard/TipTime/assets/71705375/d70d6d4b-525b-4296-a19d-f57587d1414c)

Однако вы хотите, чтобы они вводили в EditText только числа, поскольку поле представляет денежную величину.

 6. Сотрите слово text, но оставьте кавычки.

 7. Начните вводить number вместо него. После ввода "n" Android Studio показывает список возможных дополнений, которые включают "n".

![888](https://github.com/gipnozhard/TipTime/assets/71705375/fe586084-0bd6-4ef7-81fe-5be3584fd30d)

 8. Выберите numberDecimal, который ограничивает их числами с десятичной запятой.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/54134607-1f50-4418-8d75-034403fd5257)

Чтобы ознакомиться с другими вариантами типов ввода, см. раздел Укажите тип метода ввода в документации разработчика.

Необходимо внести еще одно изменение, поскольку полезно отобразить некоторую подсказку относительно того, что пользователь должен ввести в это поле.

 9. Добавьте hint атрибут к EditText, описывающий, что пользователь должен ввести в это поле.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/09079e79-08c1-457e-a9a2-583cf17271c6)

Вы также увидите обновление Редактора дизайна.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/6fcd632a-47d5-48d8-abaa-81364f128cdb)

 10. Запустите свое приложение в эмуляторе. Оно должно выглядеть следующим образом:

![image](https://github.com/gipnozhard/TipTime/assets/71705375/072c3ce9-3fbd-4658-9301-4863647a83ab)

Отличная работа! Пока мало что получается, но вы хорошо начали и немного отредактировали XML. XML для вашего макета должен выглядеть примерно так.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/e0adf970-9f72-4930-8883-74b78e9dd753)

### Добавить служебный вопрос

На этом шаге вы добавите TextView к подсказке с вопросом "Как прошел сервис?" Попробуйте ввести это без копирования / вставки. Рекомендации Android Studio должны вам помочь.

 1. После закрытия EditText тега /> добавьте новую строку и начните печатать <TextView.

 2. Выберите TextView из предложенных, и Android Studio автоматически добавит layout_width и layout_height атрибуты для TextView.

 3. Выберите wrap_content для обоих вариантов, так как вам нужно, чтобы размер TextView был таким же большим, как текстовое содержимое внутри него.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/5467ca88-2601-4493-97bc-ce4f111d2c64)

 4. Добавьте text атрибут с помощью "How was the service?"

![image](https://github.com/gipnozhard/TipTime/assets/71705375/67bdacc2-dbdd-4f34-ac3d-3625c07e1473)

 5. Закройте тег с помощью />.

 6. Обратите внимание в редакторе дизайна, что TextView перекрываетEditText.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/b050b2f0-bb5a-48e4-9319-a22a9cd97856)

Это выглядит неправильно, поэтому вы добавите ограничения на TextView следующем. Подумайте, какие ограничения вам нужны. Где TextView должны располагаться по горизонтали и вертикали? Вы можете посмотреть скриншот приложения, который поможет вам в этом.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/902d1007-e74e-4fa6-a2e8-72d4da78f975)

По вертикали вы хотите, чтобы текстовое поле TextView было ниже текстового поля "Стоимость обслуживания". По горизонтали вы хотите, чтобы TextView оно было выровнено по начальному краю родительского поля.

 7. Добавьте горизонтальное ограничение к TextView, чтобы ограничить его начальный край начальным краем родительского элемента.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/dbf1176f-0102-4785-bc7d-0fdc7adef7d6)

 8. Добавьте вертикальное ограничение к TextView, чтобы ограничить верхний край TextView нижней границы стоимости обслуживания View.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/2b7e6838-c907-4463-9310-6ee6ede95ed1)

Обратите внимание, что в @id/cost_of_service нет плюса, потому что идентификатор уже определен.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/5cc56fae-d75f-4629-ad1a-75a749274aeb)

Это выглядит не лучшим образом, но пока не беспокойтесь об этом. Вы просто хотите убедиться, что все необходимые элементы отображаются на экране и функциональность работает. Вы исправите, как это выглядит, в следующих кодовых таблицах.

 9. Добавьте идентификатор ресурса в TextView. Вам нужно будет обратиться к этому представлению позже, когда вы добавите больше представлений и свяжете их друг с другом.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/59e43d16-7d8c-42d7-b4a0-f228442d7982)

На этом этапе ваш XML-файл должен выглядеть следующим образом.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/60918e10-367c-4465-a79e-88bd78313757)

## 5. Добавление параметров подсказок

Далее вы добавите переключатели для различных вариантов подсказок, которые пользователь может выбрать.

Должно быть три варианта:

 * Потрясающе (20%)
 
 * Хорошо (18%)

 * Хорошо (15%)

Если вы не уверены, как это сделать, вы можете выполнить поиск в Google. Это отличный инструмент, который разработчики используют, когда они застревают.

 1. Выполните поиск в Google по radio button android. Лучший результат - руководство с сайта разработчиков Android о том, как использовать переключатели — идеально!

![image](https://github.com/gipnozhard/TipTime/assets/71705375/8f6c3bea-6477-4396-81ed-27ce6c302c21)

 2. Просмотрите руководство по переключателям.

Прочитав описание, вы можете убедиться, что можете использовать RadioButton элемент пользовательского интерфейса в своем макете для каждого нужного вам переключателя. Кроме того, вам также необходимо сгруппировать переключатели внутри RadioGroup, поскольку одновременно можно выбрать только один вариант.

Существует некоторый XML, который выглядит так, как будто он соответствует вашим потребностям. Прочтите его и посмотрите, RadioGroup является ли родительский вид и RadioButtons являются ли дочерние виды в нем.

 3. Вернитесь к своему макету в Android Studio, чтобы добавить RadioGroup и RadioButton в свое приложение.

 4. После TextView элемента, но все еще внутри ConstraintLayout, начните вводить <RadioGroup. Android Studio предоставит полезные рекомендации, которые помогут вам заполнить XML.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/cb5c3694-d7d7-4438-9bf2-d51404853e55)

 5. Установите для layout_width и layout_height RadioGroupзначение wrap_content.

 6. Добавьте идентификатор ресурса, установленный в @+id/tip_options.

 7. Закройте начальный тег с помощью >.

 8. Android Studio добавляет </RadioGroup>. Как и ConstraintLayout, у RadioGroup элемента внутри будут другие элементы, поэтому вы можете захотеть переместить его в отдельную строку.

![1111111111](https://github.com/gipnozhard/TipTime/assets/71705375/44b73de3-3c28-407d-b3da-2cc6066ffbb4)

 9. Ограничьте RadioGroup под служебным вопросом (по вертикали) и в начале родительского вопроса (по горизонтали).

 10. Установите для android:orientation атрибута значение vertical. Если вы хотите, чтобы RadioButtons располагались в ряд, вы бы установили ориентацию на horizontal.

XML для RadioGroup должен выглядеть следующим образом:

![image](https://github.com/gipnozhard/TipTime/assets/71705375/c8747415-e00f-4150-a488-853bc2351b77)

### Добавление радиокнопок

 1. После последнего атрибута RadioGroup, но перед </RadioGroup> конечным тегом добавьте RadioButton.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/53a3b1de-21c3-470c-af77-cc3ce0689670)

 2. Установите для layout_width и layout_height значение wrap_content.

 3. Присвойте @+id/option_twenty_percentидентификатору RadioButton ресурса.
 
 4. Установите для текста значение Amazing (20%).

 5. Закройте тег с помощью />.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/71d2f213-aa06-4d22-8b2c-ad4e6f003562)

![image](https://github.com/gipnozhard/TipTime/assets/71705375/917d8cd4-df1c-4cb2-9841-88121f8a7eb6)

Теперь, когда вы добавили один из них RadioButton, можете ли вы изменить XML, чтобы добавить еще 2 переключателя для параметров Good (18%) и Okay (15%)?

Вот как выглядит XML для RadioGroup и RadioButtons:

![image](https://github.com/gipnozhard/TipTime/assets/71705375/4db068d7-72f7-4976-acb3-434ecb77da64)

![image](https://github.com/gipnozhard/TipTime/assets/71705375/17c5d99d-93b3-4b5b-a6d1-275e8a332e89)

### Добавьте выбор по умолчанию

В настоящее время ни один из параметров подсказки не выбран. Было бы неплохо выбрать один из параметров переключателя по умолчанию.

В RadioGroup есть атрибут, с помощью которого вы можете указать, какая кнопка должна быть отмечена изначально. Она называется checkedButton, и вы устанавливаете для нее идентификатор ресурса переключателя, который хотите выбрать.

 1. sНа RadioGroupустановите для android:checkedButton атрибута значение @id/option_twenty_percent.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/66121556-cafb-4c1a-b53c-15c17c1e07ba)

Обратите внимание в редакторе дизайна, что макет был обновлен. Опция чаевых в размере 20% выбрана по умолчанию — круто! Теперь это начинает выглядеть как калькулятор чаевых!

![image](https://github.com/gipnozhard/TipTime/assets/71705375/c8327b97-5af6-4185-ab05-2d2ea29790c2)

Вот как выглядит XML на данный момент:

<?xml version="1.0" encoding="utf-8"?>
<androidx.constraintlayout.widget.ConstraintLayout 
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="16dp"
    tools:context=".MainActivity">

    <EditText
        android:id="@+id/cost_of_service"
        android:hint="Cost of Service"
        android:layout_height="wrap_content"
        android:layout_width="160dp"
        app:layout_constraintStart_toStartOf="parent"
        app:layout_constraintTop_toTopOf="parent"
        android:inputType="numberDecimal"/>

    <TextView
        android:id="@+id/service_question"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:text="How was the service?"
        app:layout_constraintTop_toBottomOf="@id/cost_of_service"
        app:layout_constraintStart_toStartOf="parent" />

    <RadioGroup
        android:id="@+id/tip_options"
        android:checkedButton="@id/option_twenty_percent"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        app:layout_constraintTop_toBottomOf="@id/service_question"
        app:layout_constraintStart_toStartOf="parent"
        android:orientation="vertical">

        <RadioButton
            android:id="@+id/option_twenty_percent"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Amazing (20%)" />

        <RadioButton
            android:id="@+id/option_eighteen_percent"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Good (18%)" />

        <RadioButton
            android:id="@+id/option_fifteen_percent"
            android:layout_width="wrap_content"
            android:layout_height="wrap_content"
            android:text="Okay (15%)" />
    </RadioGroup>
</androidx.constraintlayout.widget.ConstraintLayout>

## 6. Завершите остальную часть макета
Теперь вы переходите к последней части макета. Вы добавите Switch, Button и a TextView для отображения суммы чаевых.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/a1d50c2f-7338-4f2e-ac26-47515fca3af0)

№№№ Добавьте переключатель для округления подсказки в большую сторону

Далее вы будете использовать Switch виджет, позволяющий пользователю выбрать "да" или "нет" для округления подсказки.

Вы хотите, чтобы Switch файл был такой же ширины, как родительский, поэтому вы можете подумать, что ширина должна быть установлена равной match_parent. Как отмечалось ранее, вы не можете настроить match_parent элементы пользовательского интерфейса в ConstraintLayout. Вместо этого вам нужно ограничить начальный и конечный края представления и установить ширину равной 0dp. Установка значения width в 0dp позволяет системе не вычислять ширину, а просто попытаться соответствовать ограничениям, которые есть в представлении.

-----------------------------------------------------------------

Примечание: Вы не можете использовать match_parent ни для одного представления в ConstraintLayout. Вместо этого используйте 0dp, что означает ограничения соответствия.

-----------------------------------------------------------------

 1. Добавьте Switch элемент после XML для RadioGroup.

 2. Как отмечалось выше, установите layout_width значение 0dp.

 3. Установите layout_height значение wrap_content. Это сделает Switch вид таким же высоким, как содержимое внутри.

 4. Установите для id атрибута значение @+id/round_up_switch.

 5. Установите для text атрибута значение Round up tip?. Это будет использоваться в качестве метки для Switch.

 6. Ограничьте начальный край Switch начальным краем tip_options, а конечный - концом родительского элемента.

 7. Ограничьте верхнюю часть Switch нижней частью tip_options.

 8. Закройте тег с помощью />.

Было бы неплохо, если бы переключатель был включен по умолчанию, и для этого был бы атрибут, android:checked где возможными значениями являются true (включено) или false (выключено).

 9. Установите для android:checked атрибута значение true.

Если собрать все это вместе, XML для Switch элемента будет выглядеть следующим образом:

![image](https://github.com/gipnozhard/TipTime/assets/71705375/fe5558f1-19da-4f43-b062-c16f7223395e)

-----------------------------------------------------------------

Примечание: При наведении курсора мыши на Switch элемент в вашем XML-макете в Android Studio появится предложение: "Использовать SwitchCompat из AppCompat или SwitchMaterial из библиотеки материалов". Вы реализуете это предложение в более поздней кодовой версии создания приложения tip calculator, поэтому пока можете игнорировать предупреждение.

-----------------------------------------------------------------

![image](https://github.com/gipnozhard/TipTime/assets/71705375/ef1a815d-41cc-4899-99ba-e774eca3be7f)

### Добавьте кнопку Рассчитать
Далее вы добавите Button, чтобы пользователь мог запросить расчет чаевых. Вы хотите, чтобы кнопка была такой же ширины, как родительская, чтобы горизонтальные ограничения и ширина были такими же, как у Switch.

 1. Добавьте Button после Switch.

 2. Установите ширину на 0dp, как вы делали для Switch.

 3. Установите высоту в wrap_content.

 4. Присвойте ему идентификатор ресурса @+id/calculate_button с текстом "Calculate".

 5. Ограничить верхний край Button нижним краем округлого кончика? Switch.

 6. Ограничьте начальный край начальным краем родительского файла, а конечный край конечным краем родительского файла.

 7. Закройте тег с помощью />.

Вот как выглядит XML для вычисления Button:

![image](https://github.com/gipnozhard/TipTime/assets/71705375/3a61dcbf-1226-4edf-bb6e-1147f10f5312)

![image](https://github.com/gipnozhard/TipTime/assets/71705375/bb9c4f64-6c97-47ef-84ee-80791c46b3fc)

### Добавить результат подсказки
Вы почти закончили с макетом! На этом шаге вы добавите TextView результат подсказки, поместив его под кнопкой Рассчитать и выровняв по концу, а не по началу, как в других элементах пользовательского интерфейса.

 1. Добавьте файл TextView с идентификатором ресурса по имени tip_result и текстом Tip Amount.

 2. Ограничьте конечный край TextView конечным краем родительского файла.

 3. Сведите верхний край к нижнему краю кнопки Рассчитать.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/281d8ae0-c15f-492b-a57f-146a6bc7377f)

![image](https://github.com/gipnozhard/TipTime/assets/71705375/f7a43526-5eda-4052-bfd4-b79d1c59dbae)

 4. Запустите приложение. Оно должно выглядеть так, как показано на этом скриншоте.

![image](https://github.com/gipnozhard/TipTime/assets/71705375/58f763bb-b14b-4d78-8cc6-a1f28e935ab9)

Отличная работа, особенно если вы впервые работаете с XML!

Обратите внимание, что приложение может выглядеть не совсем так, как на скриншоте, поскольку шаблоны могли быть изменены в более поздней версии Android Studio. Кнопка Рассчитать пока ничего не делает, но вы можете ввести стоимость, выбрать процент чаевых и переключить опцию округления чаевых в большую сторону. Ты сделаешь рассчитать работают кнопки в следующем codelab, так что не забудьте вернуться за ней!








































