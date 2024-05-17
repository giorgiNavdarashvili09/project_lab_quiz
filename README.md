# Quizz App - ნაწილი I

## I - რას გავაკეთებთ?

ჩვენ ავაწყობთ ინფორმაციულ მობაილურის აპლიკაციას ონლაინ უსაფრთხოებაზე. აპლიკაციაში გვექნება კონტენტი სხვადასხვა თემის გარშემო ონლაინ უსაფრთხოებაზე. ყოველი თემის შემდეგ მომხმარებელს შეეძლება გაიაროს მინი ქვიზი განხილულ თემებზე. ქვევით მოცემულია ჩვენი აპლიკაციის სქრინები მოკლე აღწერასთან ერთად:

HomeScreen - მოცემული გვაქვს სია, რომელშიც ჩამოთვლილია ყველა იმ თემის სათაური, რასაც აპლიკაციაში განვიხილავთ.

ContentScreen - მოცემულია ინფორმაცია ერთი კონკრეტული თემის გარშემო ონლაინ უსაფრთხოებაზე.

QuizScreen - მომხმარებელს შეეძლება გაიაროს მინი ქვიზი განვლილ თემაზე.

SettingsScreen - ამ ეტაპზე მომხმარებელს შეეძლება აირჩიოს აპლიკაციის ნათელი/მუქი დიზაინი.

##  II - ვქმნით პროექტს
შევდივართ [Flutlab.io](https://flutlab.io/) პლათფორმაზე ჩვენს ექაუნთზე. შემდეგ create project ღილაკის დახმარებით ვქმნით ახალ პროექტს

![](images/create_project.PNG)

ვირჩევთ Hello World template_ს

![](images/selecting_template.PNG)

ვუთითებთ პროექტის სახელს და ვაწვებით create ღილაკს

![](images/project_name.PNG)

ბოლოს კი ვირჩევთ ჩვენს მიერ შექმნილ პროექტს Workspace ში

![](images/selecting_project.PNG)

## III - ვქმნით აპლიკაციის ზოგად სტრუქტურას

ახლა მოდით შევქმნათ პროექტის ზოგადი სტრუქტურა: შევმნათ საჭირო ფოლდერები და ფაილები, რომლებიც დაგვეხმარება ჩვენი კოდის სტანდარტების მიხედვით დაყოფაში.

პირველ რიგში შექმენი სურატზე მოცემული ფოლდერები და ფაილები შენი პროექტის lib ფოლდერში: 

![](images/project_structure.PNG)


## IV - აპლიკაციის ინფორმაციის მოდელირება
სანამ აპლიკაციის ვიზუალურ მხარეზე ვიზრუნებდეთ, მოდით შევქმნათ რამდენიმე კლასი სადაც აღვწერთ იმ ინფორმაციას/ობიექტებს, რომლებიც ჩვენს აპლიკაციაში გამოჩნდება.

content_model.dart ფაილში შევქნათ  კლასი სახელად Chapter :

```dart
class Chapter {
  final String title;
  final List<ChapterParagraph> paragraphs;

  Chapter({
    required this.title,
    required this.paragraphs,
  });
}
```

Chapter კლასი შედგება თავის სათაურისა და ChapterParagraph ობიექტების სიისაგან. ამ ინფორმაციებს კონსტრუქტორში ვითხოვთ პარამეტრების სახით.

და ბოლოს ისევ ამ ფაილში შექმენი კლასი სახელად ChapterParagraph :

```dart
class ChapterParagraph {
  final String paragraphTitle;
  final String paragraph;

  ChapterParagraph({
    required this.paragraphTitle,
    required this.paragraph,
  });
}
```

ეს კლასი აღწერს ერთი თავის ერთ ცალ პარაგრაფს და მის სათაურს.

ობიექტების სტრუქტურა უკვე აღვწერეთ ახლა გადავიდეთ data.dart ფაილში და ამ კლასების დახმარებით შევქმნათ ობიექტები, რომლებიც შეინახავენ ჩვენი აპლიკაციის ინფორმაცაიას.

data.dart ფაილში შევქმენი ცვლადი სახელად appContent, რომელიც საწყის ეტაპზე არანაირ ინფორმაციას არ შეიცავს. ყურადღებით დააკვირდი ამ ცვლადის ზოგად სტრუქტურას.
```dart
import 'package:quiz_app/models/content_model.dart';

final List<Chapter> appContent = [
  Chapter(
    title: '',
    paragraphs: [
      ChapterParagraph(
        paragraphTitle: '',
        paragraph: '',
      ),
      ChapterParagraph(
        paragraphTitle: '',
        paragraph: '',
      ),
      ChapterParagraph(
        paragraphTitle: '',
        paragraph: '',
      ),
    ],
  ),
];

```

 შემდეგ კი იგივე ცვლადი უკვე ინფორმაციით შევსებული შეგიძლია შემდეგ ფაილში ნახო: [data.dart](data.dart) 

 რათქმაუნდა შენს პროექტში შეგიძლია შეიტანო შენთვის სასურველი კონტენტი სამოქალაქო განათლებიდან

##  V - HomeScreen
home_screen.dart ფაილში შექმენი stateless ვიჯეტი სახელად HomeScreen, შემდეგ კი main.dart ფაილში MaterialApp ვიჯეტის home პარამეტრის მნიშვნელობათ გადაეცი HomeScreen კონსტრუქტორი:

საწყის ეტაპზე ჩვენი home_screen.dart ფაილი ასე გამოიყურება:

```dart
import 'package:flutter/material.dart';

class HomeScreen extends StatelessWidget {
  const HomeScreen({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return const Placeholder();
  }
}

```

ხოლო main.dart ფაილი კი ასე:

```dart
import 'package:flutter/material.dart';
import 'package:quiz_app/screens/home_screen.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return const MaterialApp(
      home: HomeScreen(),
    );
  }
}

```

main.dart ფაილში მიაქციე ყურადღება home_screen.dart ფაილის import ინსტრუქციას. იმ შემთხვევაში თუ შენი პროექტის სახელი განხვავედება ჩემისგან ეს ინსტრუქციაც განსხვავებული იქნება.

ახლა კი HomeScreen ვიჯეტში შევიტანოთ ონლაინ უსაფრთხოებაზე თავების სათაურები ListView ვიჯეტის გამოყენებით. საწყის ეტაპზე გამოვიყენოთ მხოლოდ Text ვიჯეტი სათაურების ვიზუალურად გამოსაჩენად:

```dart
import 'package:flutter/material.dart';
import 'package:quiz_app/data/data.dart';

class HomeScreen extends StatelessWidget {
  const HomeScreen({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      body: ListView.builder(
        itemBuilder: (context, index) {
          return Text(appContent[index].title);
        },
        itemCount: appContent.length,
      ),
    );
  }
}

```

როგორც ხედავთ დავამატეთ Scaffold ვიჯეტი და მის body პარამეტრში აღვწერეთ ListView ობიექტი. ListView_ს თითოეული ელემენტი კი არის Text ვიჯეტი.
Text ვიჯეტის მნიშვნელობად ვიყენებთ data.dart ფაილში აღწერილ (რომელიც აუცილებლად უნდა დავაიმპორტოთ) appContent ცვლადს და ინდექსის დახმარებით მოგვაქვს title პარამეტრის მნიშვნელობები

ამის შემდეგ თუკი ჩვენს აპლიკაციას გავუშვებთ ემულატორზე ის ასე გამოიყურება:

![](images/home_screen_text.PNG)

სანამ ListView ვიჯეტის ელემენტების ვუზუალზე ვიზრუნებდეთ მოდით დავამატოთ AppBar ვიჯეტი და გამოვაჩინოთ აპლიკაციის სახელიც HomeScreen ვიჯეტში. ამისათვის Scaffold ვიჯეტში დავამატოთ appBar პარამეტრი, რომელიც მნიშვნელობად AppBar ობიექტს ელოდება.

```dart
import 'package:flutter/material.dart';
import 'package:quiz_app/data/data.dart';

class HomeScreen extends StatelessWidget {
  const HomeScreen({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        leading: const Icon(
          Icons.laptop_chromebook,
          color: Colors.green,
          size: 32,
        ),
        title: const Text('Online Security'),
        centerTitle: true,
      ),
      body: ListView.builder(
        itemBuilder: (context, index) {
          return Text(appContent[index].title);
        },
        itemCount: appContent.length,
      ),
    );
  }
}

```

AppBar ვიჯეტს სამი პარამეტრი გავუწერეთ:
 - leading - მნიშვნელობად გადავეცით Icon ობიექტი, რომელსაც თავის მხრივ გავუწერეთ სურათი/იქონი, ფერი და ზომა
 - title - მნიშვნელობად გადავეცით Text ვიჯეტი, აპლიკაციის სახელით
 - centerTitle - მნიშვნლობად გადავეცით true რის შედეგადაც აპლიკაციის სათაური გაიწერნტრა ჰორიზონტალურად AppBar ვიჯეტში.

 დავუბრუნდეთ ჩვენს ListView_ს ელემენტებს. ყოველთვის კარგი აზრია ეკრანის კომპონენტების ცალცლაკე ვიჯეტებად/ფაილებში დანაწევრება. ამისთვის შეგვიძლია კურსორი გავაჩეროთ itemBuilder პარამეტრის ფუნქციაში არსებულ Text ვიჯეტზე, შემდეგ ctrl + . შორთქათის დახმარებით გამოვიძახოთ დამხმარე ფანჯარა და ავირჩიოთ Extract Widget გამოსულ ფანჯარაში მივუთითოთ ვიჯეტის სახელი: ჩემს შემთხვევაში დავარქვი HomeMenuItem. ამის შემდეგ ჩვენს კოდში ორ ცვლილებას აღმოვაჩენთ.

 1. ფაილის ბოლოში დაემატა ახალი კლასი სახლეად HomeMenuItem. ამ ვიჯეტის build მეთოდში სწორედ ჩვენი Text ვიჯეტი ბრუნდება
 2. itemBuilder პარამეტრში გადაწოდებულ ფუნქციაში ჩვენი Text ვიჯეტი შეიცვალა ახლად შექმნილი HomeMenuItem ვიჯეტის კონსტრუქტორით.

 ```dart
import 'package:flutter/material.dart';
import 'package:quiz_app/data/data.dart';

class HomeScreen extends StatelessWidget {
  const HomeScreen({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        leading: const Icon(
          Icons.laptop_chromebook,
          color: Colors.green,
          size: 32,
        ),
        title: const Text('Online Security'),
        centerTitle: true,
      ),
      body: ListView.builder(
        itemBuilder: (context, index) {
          return HomeMenuItem();
        },
        itemCount: appContent.length,
      ),
    );
  }
}

class HomeMenuItem extends StatelessWidget {
  const HomeMenuItem({
    super.key,
  });

  @override
  Widget build(BuildContext context) {
    return Text(appContent[index].title);
  }
}

 ```

 ამ ცვლილების შემდეგ ჩვენს კოდში სინტაქსური შეცდომაა. საქმე ისაა, რომ HomeMenuItem იყენებს index ცვლადს რომელიც აღწერილია HomeScreen კლასში.
 ამ პრობლემის გადაჭრა მარტივად შეგვიძლია. HomeMenuItem კლასს დავამატოთ ახალი ცვლადი სახელად index და ეს ინფორმაცია მოვითხოვოთ კონსტრუქტორში. ბოლოს კი HomeMenuItem კონსტუქტორის გამოძახებისას გადავაწოდოთ ეს ინფორმაცია. ამ ცვლილებების შეტანის შემდეგ მთლიანი home_screen.dart ფაილი ასე გამოიყურება:

 ```dart
import 'package:flutter/material.dart';
import 'package:quiz_app/data/data.dart';

class HomeScreen extends StatelessWidget {
  const HomeScreen({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        leading: const Icon(
          Icons.laptop_chromebook,
          color: Colors.green,
          size: 32,
        ),
        title: const Text('Online Security'),
        centerTitle: true,
      ),
      body: ListView.builder(
        itemBuilder: (context, index) {
          return HomeMenuItem(index: index);
        },
        itemCount: appContent.length,
      ),
    );
  }
}

class HomeMenuItem extends StatelessWidget {
  final int index;
  const HomeMenuItem({
    super.key,
    required this.index,
  });

  @override
  Widget build(BuildContext context) {
    return Text(appContent[index].title);
  }
}

 ```

 და ბოლოს მოდით ეს ვიჯეტი (HomeMenuItem) გავიტანოთ ცალკე ფაილში. lib ფოლდერში დავამატოთ components ფოლდერი. components ფოლდერში კი შევქმნათ ფაილი სახელად home_menu_item.dart გადავაკოპიროთ ჩვენი ვიჯეტი ახლად შექმნილ ფაილში და დავამატოთ import ინსტრუქცია material.dart ფაილის. ასევე დავაიმპორტოთ data.dart ფაილი.
 რაც შეეხება home_screen.dart ფაილს, აქ უნდა დავაიმპორტოთ ახლად შექმნილი home_menu_item.dart ფაილი. ამ ცვლილებების შემდეგ home_menu_item.dart ფაილი ასე გამოიყურება:

 ```dart
import 'package:flutter/material.dart';

import '../data/data.dart';

class HomeMenuItem extends StatelessWidget {
  final int index;
  const HomeMenuItem({
    super.key,
    required this.index,
  });

  @override
  Widget build(BuildContext context) {
    return Text(appContent[index].title);
  }
}

 ```

 ხოლო home_screen.dart ფაილი ასე:

 ```dart
import 'package:flutter/material.dart';
import 'package:quiz_app/data/data.dart';

import '../components/home_menu_item.dart';

class HomeScreen extends StatelessWidget {
  const HomeScreen({Key? key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        leading: const Icon(
          Icons.laptop_chromebook,
          color: Colors.green,
          size: 32,
        ),
        title: const Text('Online Security'),
        centerTitle: true,
      ),
      body: ListView.builder(
        itemBuilder: (context, index) {
          return HomeMenuItem(index: index);
        },
        itemCount: appContent.length,
      ),
    );
  }
}

 ```

 ამ ცვლილებას სამი დადებითი მხარე აქვს. პირველ რიგში კოდი დავყავით შედარებით პატარა ზომის მარტივად სამართავ ფაილებად. მეორე პლიუსი აპლიკაციის პერფორმანსთან არის კავშირში და მომდევნო გაკვეთილებში განვიხილავთ. მესამე კი ის არის რომ ამავე ვიჯეტის გამოყენება უკვე აპლიკაციის ნებისმიერ ნაწილში შეგვიძლია იმდენჯერ რამდენჯერაც დაგვჭირდება.

 ახალ კი გადავინაცვლოთ HomeMenuItem ვიჯეტში და დავხვეწოთ ის ვიზუალურად. პირველ რიგში Text ვიჯეტი ჩავსვათ ListTile ვიჯეტში. child პარამეტრი ამ ვიჯეტს არ აქვს და პარამეტრის სახელი title_ით შევცვალოთ. ListTile ვიჯეტი თავის მხრივ ჩავსვათ Card ვიჯეტში.

## VI - SettingsScreen

## VII - ContentScreen

## VIII - QuizScreen

