# UBCooks Design Specification

Ethan Hu, Austin Zhai, Shlok Lande, Richard Huang, Devaansh Sharma

## Problem

First-year residents at UBC eat most of their meals in campus dining halls. Menus change daily and differ across Totem Park, Orchard Commons, and Place Vanier. Many students use Nutrislice each day to check what food is being served. However, to switch between dining halls, students must click back and forth between pages to see what their food options are for that day. The interface is also inefficient, with certain sections being larger than they need to be. Furthermore, there is no way for students to see whether dishes are popular or not. How can this data on which dishes are served at each dining hall be presented in a more effective way so that students can save time on deciding where or what they will eat?

## Solution

The solution is UBCooks, a web app that pulls menus from Nutrislice for all three first-year dining halls and presents them more clearly. Users can access all dining hall menus from the homepage using buttons, and unavailable stations will be clearly marked. Furthermore, it will prioritize the users' preferences by allowing them to filter through dietary restrictions and have a rating system so they can see what their peers think of it. It will also take the users' ratings into consideration and have an email alert system whenever a dish they rated highly or the community has rated is coming back to a dining hall.

## Sample Layout (Web App)

### Menu

```text
┌──────────────────────────────────────────────────────────────────────────┐
│ [logo] UBCooks                Menu   Top Rated   Favourites   Sign in    │
├──────────────────────────────────────────────────────────────────────────┤
│ Today · Fri, Oct 16                                                      │
│                                                                          │
│ [ Totem Park ] [ Orchard Commons ] [ Vanier ]                            │
│ ( Breakfast )( Lunch )(•Dinner•)                                         │
│                                                                          │
│ Filters: Vegetarian · No Milk   [Edit]  [Show all]                       │
│ Showing 14 of 37 foods                                                   │
│                                                                          │
│ GRILL                                                                    │
│ ┌──────────────────────────────────────────────────────────────────────┐ │
│ │ Impossible Kimchi Burger                                      ♡      │ │
│ │ (Vegan) (Soy) (Wheat) (Sesame)                                       │ │
│ │ 4.3 (12 ratings)                                       [Rate]        │ │
│ └──────────────────────────────────────────────────────────────────────┘ │
│ MEDITERRANEAN                                                            │
│ ┌──────────────────────────────────────────────────────────────────────┐ │
│ │ Crispy Cauliflower Bowl                                       ♥      │ │
│ │ (Vegan) (Made Without Gluten) (Sesame)                               │ │
│ │ No ratings yet                                         [Rate]        │ │
│ └──────────────────────────────────────────────────────────────────────┘ │
│ PIZZA                                                                    │
│ Not available today.                                                     │
└──────────────────────────────────────────────────────────────────────────┘
```

This is the landing page. The user will see this upon visiting the website. We intend to make the navigation as intuitive as possible. It shows the current date with an option to select the dining hall and the respective menus. Within the respective menus, it shows each station with what it is serving, ratings, and an option to favourite a dish (if the user is signed in). The user can access the Menu, Top Rated, and Favourites through the navigation bar at the top. To access Top Rated and Favourites, and to rate dishes, the user needs to sign in using the navigation bar as well. For the filters, we intend to show only the relevant foods by default, assuming the user is familiar with common dining halls. There will also be features such as filtering by highest rated or by favourites.

### Sign In

```text
┌────────────────────────────────────────────────────────────────┐
│ Sign in to UBCooks                                             │
│ {context message, if any}                                      │
│                                                                │
│ Email  [______________________]                                │
│                                                                │
│ [ Email me a sign-in link ]                                    │
│                                                                │
│ No password needed. We'll email you a link that signs you in.  │
└────────────────────────────────────────────────────────────────┘
```

This is the Sign In page. We intend to keep it as minimal as possible ensuring a seamless experience. This means that we will not require any password for login or signup, an email link will suffice. Additionally, we intend to implement the profile settings/personalizations here after you have signed in. This includes being able to sign out or delete your account, adjust your preferences for alerts, and opt in and out of community alerts.

### Favourites

```text
┌──────────────────────────────────────────────────────────────────────────┐
│ Your favourites (4)                                                      │
│                                                                          │
│ ON TODAY                                                                 │
│ ♥ Crispy Cauliflower Bowl   Totem Park · Dinner           [✕]            │
│ ♥ Butter Chicken            Vanier · Lunch, Dinner        [✕]            │
│                                                                          │
│ COMING UP                                                                │
│ ♥ Greek Salad               Tue, Oct 20 · Orchard · Lunch [✕]            │
│                                                                          │
│ NOT ON MENUS THIS WEEK                                                   │
│ ♥ Pho                                                     [✕]            │
└──────────────────────────────────────────────────────────────────────────┘
```

Students can manage their favourite meals on the Favourites page by clicking the hearts on each meal. The page will also display when each of their favourite meals will be served next. If a meal is favourited and it is being served, the website will automatically email the student to notify them, based on their preferences.

### Top Rated

```text
┌──────────────────────────────────────────────────────────────────────────┐
│ Top rated by UBC residents                                               │
│ Foods with at least 3 ratings.     Filters: on [Show all]                │
│                                                                          │
│  1. Ginger Beef                  ★ 4.6 (21)          ♡                   │
│     Next: Today · Totem Park, Dinner                                     │
│  2. Crispy Cauliflower Bowl      ★ 4.6 (9)           ♥                   │
│     Next: Tue, Oct 20 · Vanier, Lunch                                    │
│  3. Corn and Cheese Quesadilla   ★ 4.4 (15)          ♡                   │
│     Not on menu this week                                                │
│  ...                                                                     │
└──────────────────────────────────────────────────────────────────────────┘
```

The top rated section will feature all the dishes that have the highest ratings historically, as well as when they will be in the dining hall next. These ratings are made by other users. Dishes with the same average rating are ranked by number of ratings. The Top Rated page also has filter options at the top so the user can pick a minimum rating and filter the results, for example to only show the top rated dishes today or only show the top rated vegan options.
