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
ms.openlocfilehash: 80487298f2c3c3a93f0083337ddb223bd68e2611
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2021
ms.locfileid: "53438038"
---
# <a name="get-started-with-app-governance-in-preview"></a>アプリ ガバナンスの使用を開始する (プレビュー版)

Microsoft Cloud App Security のアプリ ガバナンス アドオンの使用を開始するには、次の手順に従います。

1. お客様のアカウントが適切なレベルのライセンスを所有していることを確認します。 アプリ ガバナンスは、Microsoft Cloud App Security (MCAS) のアドオン機能であるため、アカウントに MCAS がスタンドアロン製品または以下の各種ライセンス パッケージの一部として存在している必要があります。
1. ポータルのアプリ ガバナンス ページにアクセスするには、以下のいずれかの管理者の役割が必要です。

## <a name="licensing-for-app-governance"></a>アプリ ガバナンスのライセンス

アプリ ガバナンスを開始する前に、「[Microsoft 365 管理センター（サブスクリプション](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)）」とアドオンを確認しなければなりません。 アプリ ガバナンスにアクセスして使用するには、組織は次のいずれかのサブスクリプションまたはアドオンを持っている必要があります。

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
| コンプライアンス リーダー | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) |  | ![チェック マーク](..\media\checkmark.png) |  | | |
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
