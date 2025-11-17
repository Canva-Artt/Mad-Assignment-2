Title: Multi-Fragment Android App with SharedPreferences

Description:
This Android app demonstrates how to store user preferences using SharedPreferences and display them across multiple fragments. The app has two main fragments: Settings (to save preferences) and Profile (to display saved preferences).

Features:

**Fragment 1 – User Settings**

User can enter username, email, password, and theme (light/dark).

Data is validated before saving.

Preferences are saved using SharedPreferences when the “Save Preferences” button is pressed.

“Reset Preferences” button clears all saved data using SharedPreferences.Editor.clear().


**Fragment 2 – Profile View**

Reads data from the same SharedPreferences file.

Displays saved username, email, and theme.

Uses onResume() to always load the latest values when the fragment is opened.


**Navigation**

MainActivity contains two buttons: “Settings” and “Profile”.

Uses FragmentManager and replace() to switch between SettingsFragment and ProfileFragment.


**SharedPreferences Implementation**

SharedPreferences file name: user_prefs

Keys used: username, email, password, theme


In SettingsFragment:

requireActivity().getSharedPreferences("user_prefs", MODE_PRIVATE)

editor.putString("key", value)

editor.apply()


In ProfileFragment:

Same SharedPreferences file is read to show the stored values.


**Persistent Data**

Because SharedPreferences is used, data stays saved even if:

The user closes the app

The app is reopened later


**Bonus Task – Reset Preferences**

In SettingsFragment, a “Reset Preferences” button:

Calls editor.clear().apply()

Clears the text fields on the screen

Shows a Toast message: “Preferences reset”


**Challenges and How I Solved Them:**

Understanding where to save data:

I used SettingsFragment to handle input and saving to SharedPreferences.

Sharing data between fragments:

Instead of passing data directly, both fragments read from the same SharedPreferences file.

Keeping data after app restart:

SharedPreferences automatically keeps data on disk. I just needed to read it again in ProfileFragment.


**Demonstration Video:**
(https://drive.google.com/file/d/1OreYxuy4S_AtCGx80NeW01iNBu9I8Ijz/view?usp=sharing)
