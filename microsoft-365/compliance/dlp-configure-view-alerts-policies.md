---
title: DLP ポリシーの通知を構成および表示する (プレビュー)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 10/15/2020
audience: ITPro
ms.topic: article
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: DLP ポリシーの通知を定義および管理する方法について説明します。
ms.openlocfilehash: addf46b27575f1a1cc062949aedb7ecdecaf7286
ms.sourcegitcommit: cdf2b8dad7db9e16afd339abaaa5397faf11807c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/21/2020
ms.locfileid: "48651475"
---
# <a name="configure-and-view-alerts-for-dlp-polices-preview"></a>DLP ポリシーの通知を構成および表示する (プレビュー)

この記事では、データ損失防止 (DLP) ポリシーにリンクされた豊富なアラートポリシーを定義する方法について説明します。 [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com/)で新しい dlp アラート管理ダッシュボードを使用して、dlp ポリシー違反のアラート、イベント、および関連するメタデータを表示する方法について説明します。

## <a name="features"></a>機能

このプレビューには、次の機能が含まれています。

-   **DLP アラート管理ダッシュボード**: [Microsoft 365 コンプライアンスセンター](https://compliance.microsoft.com/)では、このダッシュボードは次のワークロードに適用される DLP ポリシーの警告を示しています。

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   デバイス
-   **高度な通知の構成オプション**: これらのオプションは、DLP ポリシーの作成フローの一部です。 それらを使用して、豊富な警告構成を作成します。 イベント数またはリークしたデータのサイズに基づいて、1つのイベントまたは集計された警告を作成できます。

## <a name="before-you-begin"></a>開始する前に

開始する前に、必要な前提条件があることを確認してください。

-   DLP alerts 管理ダッシュボードのライセンス
-   警告の構成オプションのライセンス
-   ロール

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>DLP アラート管理ダッシュボードのライセンス

Office 365 DLP の対象となるすべてのテナントは、新しい DLP アラート管理ダッシュボードにアクセスできます。 開始するには、Exchange Online、SharePoint Online、OneDrive for business の Office 365 DLP の資格がある必要があります。 Office 365 DLP のライセンス要件の詳細については、「 [サービスからメリットを得るためにユーザーに権限を提供するライセンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)」を参照してください。

[エンドポイントの dlp](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide)パブリックプレビューに参加しているか、 [teams dlp](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams?view=o365-worldwide)の対象となっているお客様は、dlp アラート管理ダッシュボードで、エンドポイント Dlp ポリシー警告と teams dlp ポリシー警告を確認できます。

### <a name="licensing-for-alert-configuration-options"></a>警告の構成オプションのライセンス

-   **単一イベント通知構成**: E1、F1、または G1 サブスクリプション、あるいは E3 または G3 サブスクリプションを持つ組織は、アクティビティが発生するたびに通知がトリガーされるアラートポリシーのみを作成できます。
-   集計された**アラート構成**: しきい値に基づいて集計された通知ポリシーを構成するには、次のいずれかの構成を持っている必要があります。
    -   E5 または G5 サブスクリプション
    -   次の機能のいずれかを含む、E1、F1、または G1 サブスクリプション、あるいは E3 または G3 サブスクリプション。
        -   Office 365 Advanced Threat Protection プラン 2
        -   Microsoft 365 E5 Compliance 
        -   Microsoft 365 電子情報開示と監査アドオンライセンス

### <a name="roles"></a>ロール

Dlp アラート管理ダッシュボードを表示したり、DLP ポリシーのアラート構成オプションを編集したりするには、次のいずれかの役割グループのメンバーである必要があります。

-   コンプライアンス管理者
-   コンプライアンスデータ管理者
-   セキュリティ管理者
-   セキュリティ オペレーター
-   セキュリティ閲覧者

DLP アラート管理ダッシュボードにアクセスするには、[通知の管理] ロールと次のいずれかのロールが必要です。

-   DLP コンプライアンス管理
-   View-Only DLP コンプライアンス管理

## <a name="alert-configuration-experience"></a>通知の構成の環境

集計された [アラート構成オプション](#licensing-for-alert-configuration-options)の対象となっている場合は、DLP ポリシーの作成環境で次のオプションがインラインで表示されます。

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="集計された通知構成オプションの対象となっているユーザーのインシデントレポートのオプションを示すスクリーンショット。" border="false":::

これらの通知の構成オプションを使用して、警告がトリガーされるまでに DLP ルールの一致が可能になる頻度を定義する設定を構成できます。 この構成では、アクティビティがポリシー条件に一致するたびに、または特定のしきい値を超えたときに、アクティビティの数または抜き出しデータの量に基づいて警告を生成するポリシーを設定できます。

[単一イベントの警告構成オプション](#licensing-for-alert-configuration-options)の対象である場合は、DLP ポリシーの作成時に次の警告の構成オプションが表示されます。 このオプションを使用して、ユーザーアクティビティが原因で DLP ルールが一致したときに発生する通知を作成します。

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="集計された通知構成オプションの対象となっているユーザーのインシデントレポートのオプションを示すスクリーンショット。" border="false":::

## <a name="dlp-alert-management-dashboard"></a>DLP アラート管理ダッシュボード

DLP アラート管理ダッシュボードを操作するには、次の操作を行います。

1.  [Microsoft 365 コンプライアンスセンター](https://www.compliance.microsoft.com)で、[**データ損失防止**] に移動します。

2.  [ **通知** ] タブを選択して、DLP Alerts ダッシュボードを表示します。

    -   [フィルター] を選択して、通知の一覧を絞り込みます。 [ **列のカスタマイズ** ] を選択して、表示するプロパティを一覧表示します。 任意の列で、昇順または降順で通知を並べ替えることもできます。
    -   通知を選択して詳細を表示します。

        :::image type="content" source="../media/alert-details.png" alt-text="集計された通知構成オプションの対象となっているユーザーのインシデントレポートのオプションを示すスクリーンショット。" border="false":::

1.  [ **イベント** ] タブを選択して、通知に関連付けられているすべてのイベントを表示します。 詳細を表示する特定のイベントを選択できます。
    次の表に、イベントの詳細を示します。
    
    | カテゴリ          | プロパティ名                 | 説明                                                                | 該当するイベントの種類                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*イベントの詳細*||
    |      | Id                            | イベントに関連付けられている一意の ID                                        | すべてのイベント                               |
    |                   | 場所                      | イベントが検出されたワークロード                                      | すべてのイベント                               |
    |                   | アクティビティの時間              | DLP 違反を発生させたユーザーアクティビティの時間                    | すべてのイベント                               |
    |*影響を受けるエンティティ*||
    |  | User                          | DLP 違反を発生させたユーザー                                          | すべてのイベント                               |
    |                   | ホスト名                      | DLP 違反が検出されたコンピューターのホスト名              | Devices イベント                           |
    |                   | IP アドレス                    | コンピューターの IP アドレス                                                  | Devices イベント                           |
    |                   | ファイル パス                     | 違反に含まれるファイルの絶対パス                        | SharePoint、OneDrive、およびデバイスのイベント |
    |                   | 電子メール受信者              | DLP ポリシーに違反した電子メールの受信者                       | Exchange イベント                          |
    |                   | 電子メールの件名                 | DLP ポリシーに違反した電子メールの件名                          | Exchange イベント                          |
    |                   | メールの添付ファイル             | DLP ポリシーに違反した電子メールの添付ファイルの名前         | Exchange イベント                          |
    |                   | サイト所有者                    | サイト所有者の名前                                                     | SharePoint および OneDrive のイベント           |
    |                   | サイトの URL                      | SharePoint または OneDrive サイトの完全な URL                                | SharePoint および OneDrive のイベント           |
    |                   | ファイルが作成されました                  | ファイルの作成日時                                                      | SharePoint および OneDrive のイベント           |
    |                   | ファイルの最終更新日時            | ファイルが最後に変更された日時                                  | SharePoint および OneDrive のイベント           |
    |                   | ファイルのサイズ                     | ファイルのサイズ                                                           | SharePoint および OneDrive のイベント           |
    |                   | ファイル所有者                    | ファイルの所有者                                                          | SharePoint および OneDrive のイベント           |
    |*ポリシーの詳細*||
    |     | DLP ポリシーの一致            | 一致した DLP ポリシーの名前                                    | すべてのイベント                               |
    |                   | ルールの一致                  | 一致した DLP ポリシーの DLP ルールの名前                    | すべてのイベント                               |
    |                   | 検出された機密情報の種類 | DLP ポリシーの一部として検出された機密情報の種類 | すべてのイベント                               |
    |                   | 実行された処理                 | 一致する DLP ポリシーの一部として実行されるアクション                          | すべてのイベント                               |
    |                   | User オーバーライド policy          | ユーザーがポリシーヒントを使用してポリシーをオーバーライドするかどうか                | すべてのイベント                               |
    |                   | ジャスティフィケーションテキストを上書きする   | ポリシーヒントを上書きするために提供されるジャスティフィケーション                          | すべてのイベント                               |
    
1.  [機密情報の **種類** ] タブを選択して、コンテンツ内で検出された機密情報の種類に関する詳細を表示します。 詳細には、信頼度とカウントが含まれます。

2.  通知を調べた後、[**通知の管理**] を選択して状態 (アクティブ、**調査****中** **、非表示、また**は**解決**) を変更します。 また、コメントを追加して、組織内のユーザーに通知を割り当てることもできます。

    -   ワークフロー管理の履歴を表示するには、[ **管理ログ**] を選択します。
    -   通知に対して必要なアクションを実行した後、アラートの状態を [ **解決済み**] に設定します。
