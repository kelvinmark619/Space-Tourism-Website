<div align="center">

  <!-- <img src="./public/images/favicon-32x32.png" alt="logo" width="30" height="auto"> -->
  <img src="./public/images/shared/logo.svg" alt="logo" width="40" height="auto">

  <h2>Space Tourism</h2>

  <h3>
    <a href="https://space-tourism-Odunayo.vercel.app">
      <strong>View Demo</strong>
    </a> 
    || 
  </h3>

<!-- Brief -->
<p align="center">
A multi-page space tourism website — discover destinations, meet the crew, and delve into technology. 🚀🌌
</p>

<!-- Screenshot -->
<a align="center" href="https://space-tourism-Odunayo.vercel.app">

![Screenshot](./public/thumbnail-preview.jpg)

</a>

## Table of contents📚

- [Key Features](#key-features)
- [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
- [Installation](#installation)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

## Key Features🎉

Users should be able to:
- View multiple pages (Home, Destination, Crew, Technology)
- Responsive design across devices (mobile, tablet, desktop)
- Tabbed navigation for interactive content
- Smooth transitions and animations with Framer Motion

## Links
- View Demo - https://space-tourism-Odunayo.vercel.app

## My process🛠️

### Tech Stack🏗️

- React
- React router
- Styled components
- Vite

### What I Learned💡

While working on the Space Tourism Website, I faced several challenges that helped me grow as a developer. The process allowed me to deepen my understanding of different web development concepts and improve my problem-solving skills. Some of my key takeaways include:

#### Handling Dynamic Backgrounds with React Router and Styled Components

One of the tricky parts was ensuring each page had the right background image depending on where the user was. I solved this by combining React Router’s useLocation hook with styled-components. By passing the current route as a prop, I was able to switch between mobile, tablet, and desktop background images dynamically. This taught me how to make designs more adaptive and maintainable.
Improving Navigation with Conditional Redirects

###  Improving Navigation with Conditional Redirects
I also learned how to handle navigation issues with React Router. For example, when a user landed on the /crew route without choosing a specific crew member, I set up a redirect so that it would automatically show the first available crew member. I also added a fallback for invalid names to display a custom 404 page. This experience showed me the importance of guiding users smoothly and preventing navigation dead-ends.


```css
const StyledAppLayout = styled.div.withConfig({
  shouldForwardProp: (prop) => "pageLocation" !== prop,
})`
  background-image: ${(props) =>
    `url("/images/${props.pageLocation}/background-${props.pageLocation}-mobile.jpg")`};

  @media screen and (min-width: 768px) {
    background-image: ${(props) =>
      `url("/images/${props.pageLocation}/background-${props.pageLocation}-tablet.jpg")`};
  }

  @media screen and (min-width: 1024px) {
    background-image: ${(props) =>
      `url("/images/${props.pageLocation}/background-${props.pageLocation}-desktop.jpg")`};
  }

  // Additional styles...
`;
#### React Router and Conditional Redirects

Implementing conditional redirects with React Router was crucial for ensuring a smooth user experience. For instance, when a user lands on the `/crew` route without specifying a particular crew member. To address this, I implemented conditional redirects using React Router. Here's a breakdown of the solution:

```jsx
function CrewContents() {
  const crews = jsonData.crew;
  const { name: crewName } = useParams();
  const activeName = crewName || crews[0].name;
  const currentCrew = crews.find((crew) => crew.name === activeName);

  // Redirect to the first crew member if no specific crew is selected
  if (!crewName) {
    return <Navigate to={`/crew/${crews[0].name}`} replace />;
  }

  // Redirect to a 404 page if the specified crew member is not found
  if (!currentCrew) {
    return <NotFound />;
  }

  // Rest of the component rendering
  return (
    // ...
  );
}

## Installation📥

- Clone this repo:

```sh
```git clone https://github.com/Alicedicey/Space-Tourism-website.git

- Install dependencies:

```sh
npm install
```

- Build command:

```sh
npm run build
```

- Live server:

```sh
npm run dev
```

## Author👤

<b>Odunayo Amoye</b>

- Twitter - (https://www.twitter.com/Alicecodes)
- LinkedIn - (https://www.linkedin.com/in/Odunayo Amoye)
- Frontend Mentor -(https://www.frontendmentor.io/profile/Odunayo Amoye)
- Github: (https://github.com/Alicedicey)

## Acknowledgments🙏

I would like to express my gratitude to Frontend Mentor for providing the challenge and inspiration to build this project. 
