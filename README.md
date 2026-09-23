# InfinitXLab Tech Institute – Landing Page

Static landing page for InfinitXLab Tech Institute, Bhubaneswar.
Mentor: Er. Soumyajit Rout · Contact: 9337789240

Packaged as a `.war` so it can be deployed on Apache Tomcat.

## Project structure

```
infinitxlab/
├── pom.xml
└── src/main/webapp/
    ├── index.html          # the whole page (HTML + CSS + JS)
    └── WEB-INF/web.xml
```

## Build the WAR

Requires JDK 11+ and Maven.

```bash
mvn clean package
```

Output: `target/infinitxlab.war`

No Maven? A WAR is just a zip. From inside `src/main/webapp/`:

```bash
cd src/main/webapp
jar -cvf ../../../infinitxlab.war .
```

## Deploy on Tomcat

1. Delete the old `webapps/infinitxlab/` folder and old `infinitxlab.war` (if any).
2. Copy `infinitxlab.war` into Tomcat's `webapps/` folder.
3. Open `http://<server-ip>:8080/infinitxlab/`

## Edit the content

Everything lives in `src/main/webapp/index.html`:

- Phone number and WhatsApp link: search for `9337789240`
- Courses: the `#courses` section
- Colours: the `:root` variables at the top of the `<style>` block
- Demo form: sends the details to WhatsApp (no backend needed)
