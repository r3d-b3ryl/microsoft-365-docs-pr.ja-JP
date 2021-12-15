---
title: データ損失防止ポリシーのアラートの構成と表示
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
- admindeeplinkCOMPLIANCE
description: データ損失防止ポリシーのアラートを定義および管理する方法について説明します。
ms.openlocfilehash: 9b8ee897502f76dbdb63e3fbac99e4223f378a1a
ms.sourcegitcommit: b6ab10ba95e4b986065c51179ead3810cc1e2a85
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2021
ms.locfileid: "61521031"
---
# <a name="configure-and-view-alerts-for-data-loss-prevention-polices"></a>データ損失防止ポリシーのアラートを構成および表示する

データ損失防止 (DLP) ポリシーは、機密アイテムの意図しない共有を防ぐための保護措置を取る場合があります。 機密性の高いアイテムに対してアクションが実行された場合は、DLP のアラートを構成することで通知を受け取る可能性があります。 この記事では、データ損失防止 (DLP) ポリシーにリンクされているリッチ アラート ポリシーを定義する方法について説明します。 DLP ポリシー違反のアラート、イベント、および関連するメタデータを表示<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank"></a>するには、Microsoft 365 コンプライアンス センターで新しい DLP アラート管理ダッシュボードを使用する方法について説明します。

## <a name="features"></a>機能

次の機能は、この一部です。

-   **DLP アラート管理ダッシュボード**: このダッシュボード <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 コンプライアンス センター、次</a>のワークロードに適用される DLP ポリシーに関するアラートが表示されます。

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   デバイス
-   **高度なアラート構成オプション**: これらのオプションは、DLP ポリシー作成フローの一部です。 それらを使用して、リッチ アラート構成を作成します。 イベントの数または漏洩したデータのサイズに基づいて、単一イベントアラートまたは集約アラートを作成できます。

## <a name="before-you-begin"></a>始める前に

開始する前に、必要な前提条件が満たされていることを確認してください。

-   DLP アラート管理ダッシュボードのライセンス
-   アラート構成オプションのライセンス
-   役割

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>DLP アラート管理ダッシュボードのライセンス

DLP の対象となるテナントOffice 365、新しい DLP アラート管理ダッシュボードにアクセスできます。 開始するには、オンライン、オンライン、およびOffice 365の DLP のExchange Online対象SharePoint必要OneDrive for Business。 OFFICE 365 DLP のライセンス要件の詳細については、「どのライセンスがユーザーにサービスの恩恵を受ける権利を提供するか」[を参照してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)。

Teams [DLP](dlp-microsoft-teams.md)の対象となるエンドポイント[DLP](endpoint-dlp-learn-about.md)を使用しているお客様は、DLP アラート管理ダッシュボードにエンドポイント DLP ポリシーアラートと Teams DLP ポリシーアラートを表示します。

### <a name="licensing-for-alert-configuration-options"></a>アラート構成オプションのライセンス

- **単** 一イベントアラートの構成: E1、F1、または G1 サブスクリプションまたは E3 または G3 サブスクリプションを持つ組織は、アクティビティが発生する度にアラートがトリガーされる場合にのみアラート ポリシーを作成できます。
- **集約アラート構成**: しきい値に基づいて集約アラート ポリシーを構成するには、次のいずれかの構成が必要です。
  - E5 または G5 サブスクリプション
  - E1、F1、または G1 サブスクリプション、または次のいずれかの機能を含む E3 または G3 サブスクリプション。
    - Office 365 Advanced Threat Protection プラン 2
    - Microsoft 365 E5 Compliance 
    - Microsoft 365証拠開示と監査アドオン ライセンス

### <a name="roles"></a>役割

DLP アラート管理ダッシュボードを表示する場合、または DLP ポリシーでアラート構成オプションを編集する場合は、次のいずれかの役割グループのメンバーである必要があります。

-   コンプライアンス管理者
-   コンプライアンス データ管理者
-   セキュリティ管理者
-   セキュリティ オペレーター
-   セキュリティ閲覧者

DLP アラート管理ダッシュボードにアクセスするには、[アラートの管理] 役割と次のいずれかの役割が必要です。

-   DLP コンプライアンス管理
-   View-Only DLP コンプライアンス管理

## <a name="alert-configuration-experience"></a>アラート構成エクスペリエンス

集約されたアラート構成オプションの対象[](#licensing-for-alert-configuration-options)となる場合は、DLP ポリシー作成エクスペリエンスに次のオプションがインラインで表示されます。

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="集約されたアラート構成オプションの対象となるユーザーのインシデント レポートのオプションを示すスクリーンショット。" border="false":::

この構成では、アラートを生成するポリシーを設定できます。

- アクティビティがポリシー条件に一致する度に
- 定義されたしきい値を満たした場合、または超過した場合
- アクティビティの数に基づく
- exfiltrated データの量に基づく

通知メールのフラッディングを防ぐため、1 分間のタイム ウィンドウ内で発生し、同じ DLP ルールと同じ場所にあるすべての一致が、同じアラートでグループ化されます。 1 分間の集約タイム ウィンドウ機能は、次の場所で使用できます。 

- E5 または G5 サブスクリプション
- E1、F1、または G1 サブスクリプション、または次のいずれかの機能を含む E3 または G3 サブスクリプション。
    - Office 365 Advanced Threat Protection プラン 2
    - Microsoft 365 E5 Compliance 
    - Microsoft 365証拠開示と監査アドオン ライセンス
 
E1、F1、または G1 サブスクリプション、または E3 または G3 サブスクリプションを持つ組織の場合、集約タイム ウィンドウは 15 分です。

## <a name="dlp-alert-management-dashboard"></a>DLP アラート管理ダッシュボード

DLP アラート管理ダッシュボードを操作するには、次の操作を行います。

1.  [データ <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">損失Microsoft 365 コンプライアンス センター]</a>**に移動します**。

2.  [アラート] **タブを** 選択して、DLP アラート ダッシュボードを表示します。

    -   フィルターを選択して、アラートの一覧を絞り込む。 [列 **のカスタマイズ]** を選択して、表示するプロパティを一覧表示します。 また、任意の列でアラートを昇順または降順に並べ替えすることもできます。
    -   アラートを選択して詳細を表示します。

        :::image type="content" source="../media/alert-details.png" alt-text="DLP アラート管理ダッシュボードのアラートの詳細を示すスクリーンショット。" border="false":::

1.  [イベント **] タブを** 選択して、アラートに関連付けられているすべてのイベントを表示します。 特定のイベントを選択して、その詳細を表示できます。 次の表に、イベントの詳細の一部を示します。
    
    | カテゴリ          | プロパティ名                 | Description                                                                | 適用可能なイベントの種類                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*イベントの詳細*||
    |      | ID                            | イベントに関連付けられた一意の ID                                        | すべてのイベント                               |
    |                   | Location                      | イベントが検出されたワークロード                                      | すべてのイベント                               |
    |                   | アクティビティの時間              | DLP 違反を引き起こしたユーザー アクティビティの時間                    | すべてのイベント                               |
    |*影響を受け取ったエンティティ*||
    |  | ユーザー                          | DLP 違反を引き起こしたユーザー                                          | すべてのイベント                               |
    |                   | ホスト名                      | DLP 違反が検出されたコンピューターのホスト名              | デバイス イベント                           |
    |                   | IP アドレス                    | コンピューターの IP アドレス                                                  | デバイス イベント                           |
    |                   | ファイル パス                     | 違反に関連するファイルの絶対パス                        | SharePoint、OneDrive、デバイスイベント |
    |                   | 電子メール受信者              | DLP ポリシーに違反した電子メールの受信者                       | Exchangeイベント                          |
    |                   | メールの件名                 | DLP ポリシーに違反した電子メールの件名                          | Exchangeイベント                          |
    |                   | メールの添付ファイル             | DLP ポリシーに違反した電子メール内の添付ファイルの名前         | Exchangeイベント                          |
    |                   | サイト所有者                    | サイト所有者の名前                                                     | SharePointイベントOneDriveイベント           |
    |                   | サイトの URL                      | サイトまたはサイトSharePointのOneDrive URL                                | SharePointイベントOneDriveイベント           |
    |                   | ファイルが作成されました                  | ファイルの作成時間                                                      | SharePointイベントOneDriveイベント           |
    |                   | 最後に変更されたファイル            | ファイルの最後の変更時刻                                  | SharePointイベントOneDriveイベント           |
    |                   | ファイルのサイズ                     | ファイルのサイズ                                                           | SharePointイベントOneDriveイベント           |
    |                   | ファイルの所有者                    | ファイルの所有者                                                          | SharePointイベントOneDriveイベント           |
    |*ポリシーの詳細*||
    |     | DLP ポリシーの一致            | 一致した DLP ポリシーの名前                                    | すべてのイベント                               |
    |                   | 一致するルール                  | 一致した DLP ポリシーの DLP ルールの名前                    | すべてのイベント                               |
    |                   | 検出された機密情報の種類 | DLP ポリシーの一部として検出された機密情報の種類 | すべてのイベント                               |
    |                   | 実行された処理                 | 一致する DLP ポリシーの一部として実行されるアクション                          | すべてのイベント                               |
    |                   | ユーザーのオーバーロード ポリシー          | ユーザーがポリシー ヒントを使用してポリシーをオーバーロードするかどうか                | すべてのイベント                               |
    |                   | 位置合わせテキストを上書きする   | ポリシー ヒントを上書きするために提供される位置合わせ                          | すべてのイベント                               |
    
1.  [機密情報 **の種類] タブを** 選択して、コンテンツで検出された機密情報の種類に関する詳細を表示します。 詳細には、信頼度と数が含まれます。

2.  アラートを調査した後、[アラートの管理 **]** を選択して状態を変更します (**アクティブ**、 **調査**、 **却下**、または **解決済み**)。 コメントを追加して、組織内のユーザーにアラートを割り当てすることもできます。

    -   ワークフロー管理の履歴を表示するには、[管理ログ] **を選択します**。
    -   アラートに必要なアクションを実行した後、アラートの状態を [解決済み] **に設定します**。
