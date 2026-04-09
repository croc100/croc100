name: Metrics
on:
  schedule: [{cron: "0 0 * * *"}] # 매일 자정에 갱신
  workflow_dispatch: # 수동 실행 가능
jobs:
  github-metrics:
    runs-on: ubuntu-latest
    steps:
      - uses: lowlighter/metrics@latest
        with:
          token: ${{ secrets.METRICS_TOKEN }}
          user: croc100
          template: classic
          base: header, activity, community, repositories, metadata
          plugin_isocalendar: yes
          plugin_languages: yes
          plugin_habits: yes
          plugin_habits_facts: yes
          plugin_achievements: yes
