# Variable text image generator

You can enter text in your browser and download the generated image.

https://user-images.githubusercontent.com/22670303/227798003-87678e0b-2c2b-49fe-aac7-d36e8a8cc8bf.mov

## How to use

### For Developers

- Clone this repository.
  - If you want to change the repository name, change the name field in package.json as well.
- Run `pnpm dev`.
- Change styles by referring to `src/templates/Example1.tsx` or `src/templates/Example2.tsx
- Change `src/routes.ts` if you want to change the path or the text in the image.
- Change the `settings > Build and deployment > Source` in the repository to `GitHub Actions` to use it on GitHub Pages.
- You can then use it on GitHub Pages every time you push to your main branch.

### For people who download images

- Enter suitable text in the text field.
- Click the `Download` button.

## Reference

The code I used as a reference: https://codesandbox.io/s/save-as-png-f8ln1i
