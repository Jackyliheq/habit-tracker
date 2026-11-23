# Habit Quest

Habit Quest is a local-first, gamified habit tracker built with Flutter. Create
habits, complete them each day, and earn XP and coins while building streaks.
The current UI uses the dark navy card-based visual direction from
`project_blueprint`.

## MVP features

- Create, edit, and delete daily or weekly habits.
- Check in once per local calendar day.
- Track total completions and longest streak.
- Earn XP, level up, and collect coins.
- View progress on Home, Stats, and Profile screens.
- Edit your display name, choose preset avatars, or select an image from your device.
- Buy profile borders, avatar items, and automatic streak savers in the Shop.
- Persist habits, logs, and profile state locally across restarts.

The first MVP intentionally does not include authentication, cloud sync,
notifications, pets, challenges, or a full achievements system.

## Shop rules

- Gold and Sky profile borders cost 100 coins.
- Star Scout and Rocket avatars cost 75 coins.
- A Streak saver costs 150 coins.
- A Streak saver is automatically consumed when the next check-in detects
  exactly one missed day. It protects the streak but does not award XP for the
  missed day.
- New profiles start as User1 with 60 coins. A red Shop indicator appears when
  an unowned reward can be redeemed, and the 75-coin reward notice is shown
  only once.
- Shop inventory, equipped items, and saver balance are stored locally.

## Architecture

- `lib/models`: typed domain objects and serialization.
- `lib/services`: gamification rules and local persistence.
- `lib/providers`: Riverpod application state and mutations.
- `lib/theme`: shared dark theme tokens.
- `lib/main.dart`: go_router routes and the application screens.
- `lib/models/shop_item.dart`: centralized Shop catalog and prices.

## Run locally

```text
flutter pub get
flutter run
```

Run validation with:

```text
flutter analyze
flutter test
```

XP and coin balancing values are centralized in
`lib/services/gamification_service.dart`, while Shop prices are centralized in
`lib/models/shop_item.dart`, so balancing can be tuned without changing the UI.



Project ini dihentikan pada progress 65% dengan beberapa hal yang belum diimplementasikan yaitu Database/API aplikasi 
