---
title: アプリ ガバナンスの使用を開始する
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: アプリを管理するためのアプリ ガバナンス機能の使用を開始します。
ms.openlocfilehash: dc07acab3d58f8449f01f09f45c3bc78b66d0e3e
ms.sourcegitcommit: 60cc1b2828b1e191f30ca439b97e5a38f48c5169
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/23/2021
ms.locfileid: "53541207"
---
# <a name="get-started-with-app-governance-in-preview"></a>アプリ ガバナンスの使用を開始する (プレビュー版)

Microsoft Cloud App Security のアプリ ガバナンス アドオンの使用を開始するには、次の手順に従います。

1. お客様のアカウントが適切なレベルのライセンスを所有していることを確認します。 アプリ ガバナンスは、Microsoft Cloud App Security (MCAS) のアドオン機能であるため、アカウントに MCAS がスタンドアロン製品または以下の各種ライセンス パッケージの一部として存在している必要があります。
1. ポータルのアプリ ガバナンス ページにアクセスするには、以下のいずれかの管理者の役割が必要です。
1. 所属している組織のテナント登録は、[北米、欧州、アフリカ](app-governance-countries.md)のいずれかのサポート エリア内である必要があります。

## <a name="licensing-for-app-governance"></a>アプリ ガバナンスのライセンス

アプリ ガバナンスを開始する前に、「[Microsoft 365 管理センター（サブスクリプション](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/subscriptions)）」とアドオンを確認しなければなりません。 アプリ ガバナンスにアクセスして使用するには、組織は次のいずれかのサブスクリプションまたはアドオンを持っている必要があります。

- Microsoft Cloud App Security
- Microsoft 365 E5
- Microsoft 365 E5 Compliance 
- Microsoft 365 E5 Developer (Windows および電話会議なし)
- Microsoft 365 E5 Information Protection and Governance
- Microsoft 365 E5 Security
- Microsoft 365 E5 (無料通話時間付き)
- Microsoft 365 E5 (電話会議なし)
- Microsoft 365 A5 Compliance for faculty
- Microsoft 365 A5 Compliance 学生用
- Microsoft 365 A5 教職員用
- Microsoft 365 A5 児童/学生用
- Microsoft 365 A5 Information Protection and Governance 教職員用
- Microsoft 365 A5 Information Protection and Governance 児童/学生用
- Microsoft 365 A5 Security for faculty
- Microsoft 365 A5 Security 学生用
- Microsoft 365 A5 学生使用特典
- Microsoft 365 A5 (無料通話時間付き) 教職員用
- Microsoft 365 A5 (無料通話時間付き) 学生用
- Microsoft 365 A5 (電話会議なし) 教職員用
- Microsoft 365 A5 (電話会議なし) 学生用
- Microsoft 365 A5 (電話会議なし) 学生使用特典

## <a name="administrator-roles"></a>管理者の役割

アプリ ガバナンス ページを表示したり、ポリシーや設定を管理したりするには、以下のいずれかの管理者の役割が必要です。

- アプリケーション管理者
- クラウド アプリケーション管理者
- 社内管理者
- コンプライアンス管理者
- コンプライアンス データ管理者
- コンプライアンス リーダー (読み取り専用)
- グローバル閲覧者
- セキュリティ管理者
- セキュリティ オペレーター
- セキュリティ リーダー (読み取り専用)

> [!NOTE]
> グローバル管理者のみが、アプリ ガバナンスの無料試用版を有効化できます。

こちらが各役割の機能です。

| 役割 | ダッシュボードを読み取る | すべてのアプリを読み取る |ポリシーを読み取る | ポリシーを作成、更新、削除する | アラートを読み取る | アラートを更新する | 設定を読み取る | 設定を更新する | 修復を読み取る | 修復を更新する |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| アプリケーション管理者 | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |
| クラウド アプリケーション管理者 | ![チェック マーク](..\media\checkmark.png) | | | | | | | | | |
| 社内管理者 | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |
| コンプライアンス管理者 | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | |
| コンプライアンス データ管理者 | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | |
| コンプライアンス 閲覧者 | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) |  | | |
| グローバル閲覧者  | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) |  | | |
| セキュリティ管理者 | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | |
| セキュリティ オペレーター | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | |
| セキュリティ閲覧者  | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) | |
|||||||||| | |

各役割に関する詳細については、「[管理者の役割のアクセス許可](/azure/active-directory/roles/permissions-reference)」を参照してください。

## <a name="add-app-governance-to-your-microsoft-365-account"></a>Microsoft 365 アカウントにアプリ ガバナンスを追加する

既存の Microsoft 365 のお客様の場合:

1. [Microsoft 365 管理センター](https://admin.microsoft.com)で、**[請求 - サービスの購入]** に移動し、**[アドオン]** をクリックします。
1. アプリ ガバナンス カードで、**[詳細]** をクリックします。
1. **[無料試用版を開始]** をクリックします。
1. 必要な情報を入力し、選択済みのテナントにアプリ ガバナンスを追加します。 新規のお客様の場合、まずアカウントを作成するための情報を提供し、試用期間中のテナントを作成する必要があります。 これが完了すると、試用版にアプリ ガバナンスを追加できます。

Microsoft 365 の新しいお客様の場合:

1. このページの上部にある **[無料アカウント]** ボタンをクリックします。
1. **[Microsoft 365 for business を試す]** で、**1 ヶ月の無料試用版を試す]** をクリックします。

両者向け:

1. サインアップ ポータルでは、試用版に使用するメール アドレスを入力します。 既存のお客様の場合は、アカウントに関連付けられたメールを使用します。 [**次へ**] をクリックします。
1. サインインしたら、**[今すぐ試す]** をクリックして、無料体験版を入手します。
1. **[続行]** をクリックしてページを閉じ、使用番の設定を開始します。 新しいアプリ ガバナンスのお客様の場合、アプリ ガバナンスのインスタンスが利用可能になるまで、最大で 2 時間かかります。 既存のお客様については、既存のサービスに支障はありません。

  > [!NOTE]
  アカウントをお持ちでない場合は、試用版の使用を開始する前に、新しいアカウントを設定するためのメッセージが表示されます。

1. AAD テナントの利用可能なドメイン名を入力し、**[利用可能か確認]** をクリックします。 管理者の役割が自動的に割り当てられます (アプリ ガバナンスのための既存の役割がない場合)。ドメイン名の変更やテナントの追加購入は、Microsoft 365 管理センター経由で後からでも可能です。
1. アカウントへのログインに使用するユーザー名とパスワードを入力します。 [**サインアップ**] をクリックします。
1. **[今すぐ開始]** をクリックしてアプリ ガバナンスポータルに移動するか、**[サブスクリプションの管理]** をクリックして Microsoft 365 管理センターに移動します。

## <a name="add-integration-with-mcas"></a>MCAS との統合を追加 

前提条件:

- Office 365 は、Cloud App Security で接続されています。
- Office 365 Azure AD アプリが有効化されています

Cloud App Security を使用してアプリ ガバナンスの同期を有効にするには、以下の手順に従ってください。

1. Microsoft Cloud App Security ポータルに移動する - [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com)
1. 歯車アイコン (右上) をクリックし、[**設定**] を選択します。
1. [**脅威の防止**] から [**アプリ ガバナンス**] を選択します。
1. [**アプリ ガバナンスの統合を有効にする**] をクリックして、[**保存**] を選択します。

次に、MCAS で新たに有効化されたポリシーを確認します。 統合が有効化されてから新しいポリシーが表示されるまでに数分かかる場合があります。

- Microsoft 365 OAuth アプリの評価
- Microsoft 365 OAuth フィッシング検出
- Microsoft 365 OAuth アプリ ガバナンス
- MCAS ダッシュボードのアプリ ガバナンス ウィジェットを確認する
- MCAS アラートで新しく生成されたアプリ ガバナンスのアラートを確認する
- アプリ ガバナンス ポリシー一覧で MCAS M365 OAuth ポリシーを確認する
- アプリ ガバナンス アラートで新しく生成された MCAS M365 OAuth アラートを確認する

## <a name="canceling-your-trial"></a>試用版のキャンセル

プライベート プレビューに参加しておらず、アプリ ガバナンス試用版をキャンセルしたい場合は、CXE の担当者に連絡するか、以下の手順でキャンセルすることができます。

1. Microsoft 365 管理センターで、[**課金情報**] > [**お使いの製品**] の順に移動します。
1. アプリ ガバナンス試用版に移動し、3 つの点をクリックし、[**サブスクリプションのキャンセル**] を選択します。
1. 表示されるフライアウト ウィンドウで、キャンセルの理由と追加のフィードバックを入力し、[**サブスクリプションのキャンセル**] を選択します。
1. 表示されたポップアップ画面で [**サブスクリプションのキャンセル**] を選択します。 試用版がキャンセルされ、アプリ ガバナンスにアクセスできなくなり、アプリ ガバナンス データが削除されます (アプリ ガバナンスの分析情報および検出を作成するために使用されるログ データで、メールやその他のファイルは影響を受けません)。
