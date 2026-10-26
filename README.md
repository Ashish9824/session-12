# session-12

### Task 1: `Playlist` Structure for Song Details

```c
#include <stdio.h>
#include <string.h>

// Declare structure
struct Playlist {
    char title[100];
    char artist[100];
    int duration; // duration in seconds
};

int main() {
    // Initialize structure variable
    struct Playlist favoriteSong = {
        .title = "Starboy",
        .artist = "The Weeknd",
        .duration = 230 // 3 minutes 50 seconds
    };

    // Print each field
    printf("--- Spotify Song Details ---\n");
    printf("Title    : %s\n", favoriteSong.title);
    printf("Artist   : %s\n", favoriteSong.artist);
    printf("Duration : %d seconds (%d:%02d mins)\n", 
           favoriteSong.duration, 
           favoriteSong.duration / 60, 
           favoriteSong.duration % 60);

    return 0;
}

```

---

### Task 2: Array of `FoodItem` Structures (Zomato Menu)

```c
#include <stdio.h>

// Declare structure
struct FoodItem {
    char itemName[100];
    float price;
    float rating;
};

int main() {
    // Initialize an array of 3 FoodItem structures
    struct FoodItem menu[3] = {
        {"Paneer Butter Masala", 280.00f, 4.6f},
        {"Butter Naan", 45.00f, 4.4f},
        {"Veg Biryani", 220.00f, 4.3f}
    };

    printf("--- Zomato Restaurant Menu ---\n");
    for (int i = 0; i < 3; i++) {
        printf("Item %d: %-22s | Price: ₹%6.2f | Rating: %.1f ★\n", 
               i + 1, 
               menu[i].itemName, 
               menu[i].price, 
               menu[i].rating);
    }

    return 0;
}

```

---

### Task 3: Nested Structure `MovieShow` (BookMyShow)

```c
#include <stdio.h>

// Child structure: Time
struct Time {
    int hours;
    int minutes;
};

// Parent structure: MovieShow (contains nested struct Time)
struct MovieShow {
    char movie[100];
    int screen;
    struct Time showTime;
};

int main() {
    // Initialize nested structure
    struct MovieShow show = {
        "Interstellar",
        2,
        {19, 45} // 07:45 PM
    };

    // Formatted print matching 'Movie: X, Screen: Y, Time: HH:MM'
    printf("Movie: %s, Screen: %d, Time: %02d:%02d\n", 
           show.movie, 
           show.screen, 
           show.showTime.hours, 
           show.showTime.minutes);

    return 0;
}

```

---

### Task 4: Nested Structure `InstaProfile` with `Bio`

```c
#include <stdio.h>

// Child structure: Bio
struct Bio {
    char description[150];
    int age;
};

// Parent structure: InstaProfile (contains nested struct Bio)
struct InstaProfile {
    char username[50];
    int followers;
    struct Bio bio;
};

int main() {
    // Initialize InstaProfile variable
    struct InstaProfile myProfile = {
        "ashu_dev",
        1850,
        {
            "Tech enthusiast & Full Stack Developer 🚀",
            19
        }
    };

    // Display all fields
    printf("--- Instagram Profile ---\n");
    printf("Username    : @%s\n", myProfile.username);
    printf("Followers   : %d\n", myProfile.followers);
    printf("Bio Age     : %d\n", myProfile.bio.age);
    printf("Bio About   : %s\n", myProfile.bio.description);

    return 0;
}

```
