- 👋 Oi, meu nome é Roger de Brito 
- 👀 Apaixonado por tecnologia.
- 🌱 Atualmente estou estudando Python language.
- 💞️ Estou a procura de um Estágio na área de Sistemas.
- 📫 Meu LinkedIn: https://www.linkedin.com/in/roger-brito-758191150/


name: Generate Datas

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"
  workflow_dispatch:

jobs:
  build:
    name: Jobs to update datas
    runs-on: ubuntu-latest
    steps:
      # Snake Animation
      - uses: Platane/snk@master
        id: snake-gif
        with:
          github_user_name: rogergbrito
          svg_out_path: dist/github-contribution-grid-snake.svg

      - uses: crazy-max/ghaction-github-pages@v2.1.3
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
