# PDF preview and edit research
In the project directory, you can run:

### `npm start`

Runs the app in the development mode.\
Open [http://localhost:3000](http://localhost:3000) to view it in your browser.

## Foundations for research:
- [Mozilla PDF.js](https://mozilla.github.io/pdf.js/)
- [react-pdf](https://github.com/wojtekmaj/react-pdf/)

## Encountered limitations
### React-pdf
Currently, in a couple of our projects we use a React-wrapped pdf viewer called React-pdf.
After some investigation into its code base I found that react-pdf while "in-theory" is able to view annotations present in a file and has a support for annotations layer, none of my attempts have yielded any fruitful results.
**No examples** or **documentation** have been found that would show how to view annotations in a pdf file using react-pdf.
- **Pros**:
    - Easy to use
    - React-based
    - Good for simple pdf viewing
- **Cons**:
    - No support for annotations
    - No support for editing

### Mozilla PDF.js
Mozilla PDF.js is a powerful library that allows for a lot of customization and control over the pdf viewer, however at a cost of complexity and cognitive load.
- **Pros**:
    - Powerful
    - Customizable
    - Supports annotations
    - Supports editing
- **Cons**:
    - Complex. Incredibly complex.

## Possible solutions

### React-pdf
Theoretically, it is possible to make a fork of react-pdf and add support for annotations and editing. However, it's worth noting that at the time of creating this note
the exact scope of required insight is unknown. It is possible that the scope of work is too large to be feasible since beside inherent pdf.js complexity react-pdf also introduces overhead
of its own architecture and conventions.

### Mozilla PDF.js (this repository)
As per the [library's documentation](https://mozilla.github.io/pdf.js/getting_started), it is possible to use already present "Viewer" layer that can be used to view pdf files.
Maintainers of the library also encourage to use the "Viewer" as a starting point where one can modify the appearance and tweak certain behaviors(to which extent - again, no final conclusion)
However, it is worth noting that the library is incredibly complex and requires a lot of time to understand and work with.
This repository serves as a possible React wrapper for the PDF.js Viewer


## Remaining challenges
While the Viewer demonstrates capability of annotating and editing pdf files, at the time of writing this note, the exact scope of retrofit work required to upload the modified pdf file to the desired location is unknown.