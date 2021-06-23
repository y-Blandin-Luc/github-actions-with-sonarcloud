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