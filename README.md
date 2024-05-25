name: Waka Readme
on:
  # for manual workflow trigger
  workflow_dispatch:
  schedule:
    # runs every hour
    - cron: "0 */1 * * *"
jobs:
  update-readme:
    name: WakaReadme DevMetrics
    runs-on: ubuntu-latest
    steps:
      - uses: athul/waka-readme@master # this action name
        with:
          WAKATIME_API_KEY: ${{ secrets.WAKATIME_API_KEY }}
          BLOCKS: ⣀⣄⣤⣦⣶⣷⣿
          TIME_RANGE: all_time
          CODE_LANG: txt
          SHOW_MASKED_TIME: true
          LANG_COUNT: 10
          STOP_AT_OTHER: false
          COMMIT_MESSAGE: "[workflow] update stats"