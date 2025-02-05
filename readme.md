# Micro Frontends Proof of Concept (PoC)

This repository contains a Proof of Concept (PoC) demonstrating the implementation of a micro frontend architecture.  It showcases how different frontend technologies can be integrated to create a cohesive user experience.

## DEMO

https://dgkjlb4bo3qfw.cloudfront.net/

* Demonstration flow: root -> princing -> go back via App button -> login -> sign in (with credentials blank ) -> dashboard -> logout

## Overview

This PoC explores the benefits and challenges of micro frontends by building a simple web application composed of independently deployable units. The goal is to demonstrate:

* **Technology Agnosticism:** Integrating components built with different frameworks (e.g., React, Vue, Angular, or even plain JavaScript).
* **Independent Deployments:**  How individual micro frontends can be deployed and updated without affecting the entire application.
* **Code Isolation:**  Ensuring that each micro frontend's code, styles, and dependencies are isolated to prevent conflicts.
* **Team Autonomy:**  How different teams can work on separate micro frontends independently.

## Architecture

* **Container Application:**  Responsible for composing the micro frontends. Located in the `component` directory then lazy loaded into the container app.

* Each micro frontend has a function (look for mount function) that enables decoupling between MFE and container app (despite container also being written in react)

* Some dark magic being done for the routing: since most navigation libraries uses some kind of history, we're creating it then passing down to each micro frontend as prop so everybody can keep up with route being changed among several MFE's.

* The rest is webpack's doing. All projects are wrapped and build by webpack and use Module Federation.

## Technologies Used

* **[Technology 1]:**  React
* **[Integration Method]:** Webpack Module Federation
* **[Build Tool]:** Webpack
* **[Other relevant technologies]:** CSS-in-JS library

## Getting Started

1. Clone the Repository
2. Navigate to the Project Directory
3. Install Dependencies (`npm install` for each micro frontend and the container app)
4. Run the Application (`npm run dev` for each micro frontend and the container app)
