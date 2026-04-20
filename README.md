# LMS Project 👋

This is an [Expo](https://expo.dev) project with [Tailwind CSS v4](https://tailwindcss.com) and [NativeWind v5](https://www.nativewind.dev) for universal styling across iOS, Android, and Web.

## Get started

1. Install dependencies

   ```bash
   npm install --legacy-peer-deps
   ```

2. Start the app

   ```bash
   npm start
   ```

In the output, you'll find options to open the app in a

- [development build](https://docs.expo.dev/develop/development-builds/introduction/)
- [Android emulator](https://docs.expo.dev/workflow/android-studio-emulator/)
- [iOS simulator](https://docs.expo.dev/workflow/ios-simulator/)
- [Expo Go](https://expo.dev/go), a limited sandbox for trying out app development with Expo

You can start developing by editing the files inside the **app** directory. This project uses [file-based routing](https://docs.expo.dev/router/introduction).

## Tailwind CSS Setup

This project uses Tailwind CSS v4 with NativeWind v5 for styling. Here's what you need to know:

### Using Tailwind Classes

Import components from `@/tw` instead of `react-native`:

```tsx
import { View, Text, ScrollView, Pressable } from "@/tw";

export default function MyScreen() {
  return (
    <View className="flex-1 bg-white p-4">
      <Text className="text-2xl font-bold text-gray-900">
        Hello Tailwind!
      </Text>
      <Pressable className="bg-blue-500 p-4 rounded-lg mt-4">
        <Text className="text-white text-center">Press me</Text>
      </Pressable>
    </View>
  );
}
```

### Available Components

All components support the `className` prop:
- `View`, `Text`, `ScrollView`, `Pressable`
- `TextInput`, `TouchableHighlight`
- `Image` (from `@/tw/image`)
- `Animated` (from `@/tw/animated`)
- `Link` (Expo Router link with className support)

### Custom Styling

Add custom theme variables in `src/global.css`:

```css
@layer theme {
  @theme {
    --color-primary: #3b82f6;
    --font-custom: "MyFont", sans-serif;
  }
}
```

### Platform-Specific Styles

Use platform media queries in your CSS:

```css
@media ios {
  :root {
    --font-sans: system-ui;
  }
}

@media android {
  :root {
    --font-sans: normal;
  }
}
```

### Configuration Files

- `metro.config.js` - Metro bundler with NativeWind transformer
- `postcss.config.mjs` - PostCSS with Tailwind plugin
- `src/global.css` - Global Tailwind imports and theme
- `src/tw/` - CSS-wrapped React Native components

## Get a fresh project

When you're ready, run:

```bash
npm run reset-project
```

This command will move the starter code to the **app-example** directory and create a blank **app** directory where you can start developing.

### Other setup steps

- To set up ESLint for linting, run `npx expo lint`, or follow our guide on ["Using ESLint and Prettier"](https://docs.expo.dev/guides/using-eslint/)
- If you'd like to set up unit testing, follow our guide on ["Unit Testing with Jest"](https://docs.expo.dev/develop/unit-testing/)
- Learn more about the TypeScript setup in this template in our guide on ["Using TypeScript"](https://docs.expo.dev/guides/typescript/)

## Learn more

To learn more about developing your project with Expo, look at the following resources:

- [Expo documentation](https://docs.expo.dev/): Learn fundamentals, or go into advanced topics with our [guides](https://docs.expo.dev/guides).
- [Learn Expo tutorial](https://docs.expo.dev/tutorial/introduction/): Follow a step-by-step tutorial where you'll create a project that runs on Android, iOS, and the web.

## Join the community

Join our community of developers creating universal apps.

- [Expo on GitHub](https://github.com/expo/expo): View our open source platform and contribute.
- [Discord community](https://chat.expo.dev): Chat with Expo users and ask questions.
