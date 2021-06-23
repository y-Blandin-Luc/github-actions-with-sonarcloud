# SonarCloud

[SonarCloud GitHub Action](https://github.com/marketplace/actions/sonarqube-scan#sonarqube-github-action)でSonarQubeのリモートサーバーにスキャンする。

1. GitHubにパブリックリポジトリを作成して、ソースコードを入れて、ワークフローを定義する。
4. [SonarCloud](https://sonarcloud.io/)にGitHubアカウントでログインする
5. SonarCloudにプロジェクトを作成する。スキャン対象は作成したリポジトリです。
6. SonarCloudのアカウントセキュリティにtokenを生成する
7. GitHubのリポジトリに「sonar-project.properties」を作成して、SonarCloudのプロジェクトキーとOrganizationキーを設定する。
9. ワークフローに[SonarCloud Scan](https://github.com/marketplace/actions/sonarcloud-scan)を追加する
10. リポジトリ設定のsecretにSonarCloudの生成したで「SONAR_TOKEN」を追加する
11. ワークフローを実行する
12. SonarCloudに結果を確認する

SonarCloudにプロジェクトを作成後、チュートリアルがあります：
https://sonarcloud.io/project/configuration?analysisMode=GitHubActions&id=[プロジェクト名]

注意点：
- [Could not find a default branch to fall back on.](https://github.com/y-Blandin-Luc/github-actions-with-sonarcloud/runs/2891911720?check_suite_focus=true)エラーが発生場合、「sonar-project.properties」のプロジェクトキーまたはOrganizationキーを確認してください。
- [You are running CI analysis while Automatic Analysis is enabled. Please consider disabling one or the other.](https://sonarcloud.io/documentation/analysis/automatic-analysis/)エラーが発生場合、SonarCloudのプロジェクトに「SonarCloud Automatic Analysis」を無効してください。
