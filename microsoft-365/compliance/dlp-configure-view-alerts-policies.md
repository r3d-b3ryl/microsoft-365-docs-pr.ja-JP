---
title: DLP ポリシーの警告を構成および表示する (プレビュー)
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
localization_priority: Normal
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MET150
ms.custom:
- seo-marvel-apr2020
description: DLP ポリシーのアラートを定義および管理する方法について説明します。
ms.openlocfilehash: 7bc9d9b59c0424792f995be42591548b758c99ec
ms.sourcegitcommit: 89095172c9c4793d56645b4c885ac8e30936bd0a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2021
ms.locfileid: "50766422"
---
# <a name="configure-and-view-alerts-for-dlp-polices-preview"></a>DLP ポリシーのアラートの構成と表示 (プレビュー)

この記事では、データ損失防止 (DLP) ポリシーにリンクされているリッチ アラート ポリシーを定義する方法について説明します。 [Microsoft 365](https://compliance.microsoft.com/)コンプライアンス センターの新しい DLP アラート管理ダッシュボードを使用して、DLP ポリシー違反のアラート、イベント、および関連するメタデータを表示する方法について説明します。

## <a name="features"></a>機能

次の機能は、このプレビューの一部です。

-   **DLP アラート管理ダッシュボード**: [Microsoft 365 コンプライアンス](https://compliance.microsoft.com/)センターでは、このダッシュボードには、次のワークロードに適用される DLP ポリシーのアラートが表示されます。

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   デバイス
-   **高度なアラート構成オプション**: これらのオプションは、DLP ポリシー作成フローの一部です。 それらを使用して、リッチ アラート構成を作成します。 イベントの数または漏洩したデータのサイズに基づいて、単一イベントアラートまたは集約アラートを作成できます。

## <a name="before-you-begin"></a>開始する前に

開始する前に、必要な前提条件が満たされていることを確認してください。

-   DLP アラート管理ダッシュボードのライセンス
-   アラート構成オプションのライセンス
-   Roles

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>DLP アラート管理ダッシュボードのライセンス

365 DLP Office対象テナントはすべて、新しい DLP アラート管理ダッシュボードにアクセスできます。 開始するには、Exchange Online、SharePoint Online、および OneDrive for Business Office 365 DLP の対象となる必要があります。 Office 365 DLP のライセンス要件の詳細については、「どのライセンスがユーザーにサービスの恩恵を受ける権限を提供するのか」 [を参照してください](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)。

[エンドポイント](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide)DLP パブリック プレビューに参加しているお客様、または[Teams DLP](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams?view=o365-worldwide)の対象となるお客様には、DLP アラート管理ダッシュボードにエンドポイント DLP ポリシーアラートと Teams DLP ポリシーアラートが表示されます。

### <a name="licensing-for-alert-configuration-options"></a>アラート構成オプションのライセンス

-   **単** 一イベントアラートの構成: E1、F1、または G1 サブスクリプションまたは E3 または G3 サブスクリプションを持つ組織は、アクティビティが発生する度にアラートがトリガーされる場合にのみアラート ポリシーを作成できます。
-   **集約アラート構成**: しきい値に基づいて集約アラート ポリシーを構成するには、次のいずれかの構成が必要です。
    -   E5 または G5 サブスクリプション
    -   E1、F1、または G1 サブスクリプション、または次のいずれかの機能を含む E3 または G3 サブスクリプション。
        -   Office 365 Advanced Threat Protection プラン 2
        -   Microsoft 365 E5 Compliance 
        -   Microsoft 365 電子情報開示と監査アドオン ライセンス

### <a name="roles"></a>Roles

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

これらのアラート構成オプションを使用して、アラートがトリガーされる前に DLP ルールの一致が発生する頻度を定義する設定を構成できます。 この構成を使用すると、アクティビティがポリシー条件に一致するか、アクティビティの数に基づいて、または削除されたデータの量に基づいて、特定のしきい値を超えた場合にアラートを生成するポリシーを設定できます。

単一イベントアラート構成オプションの[](#licensing-for-alert-configuration-options)対象となる場合は、DLP ポリシー作成エクスペリエンスに次のアラート構成オプションが表示されます。 このオプションを使用して、ユーザー アクティビティのために DLP ルールの一致が発生する度に発生するアラートを作成します。

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="単一イベントアラート構成オプションの対象となるユーザーのインシデント レポートのオプションを示すスクリーンショット。" border="false":::

## <a name="dlp-alert-management-dashboard"></a>DLP アラート管理ダッシュボード

DLP アラート管理ダッシュボードを操作するには、次の操作を行います。

1.  Microsoft [365 コンプライアンス センターで、[](https://www.compliance.microsoft.com)データ損失防止 **] に移動します**。

2.  [アラート] **タブを** 選択して、DLP アラート ダッシュボードを表示します。

    -   フィルターを選択して、アラートの一覧を絞り込む。 [列 **のカスタマイズ]** を選択して、表示するプロパティを一覧表示します。 また、任意の列でアラートを昇順または降順に並べ替えすることもできます。
    -   アラートを選択して詳細を表示します。

        :::image type="content" source="../media/alert-details.png" alt-text="DLP アラート管理ダッシュボードのアラートの詳細を示すスクリーンショット。" border="false":::

1.  [イベント **] タブを** 選択して、アラートに関連付けられているすべてのイベントを表示します。 特定のイベントを選択して、その詳細を表示できます。
    次の表に、イベントの詳細の一部を示します。
    
    | カテゴリ          | プロパティ名                 | 説明                                                                | 適用可能なイベントの種類                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*イベントの詳細*||
    |      | ID                            | イベントに関連付けられた一意の ID                                        | すべてのイベント                               |
    |                   | 場所                      | イベントが検出されたワークロード                                      | すべてのイベント                               |
    |                   | アクティビティの時間              | DLP 違反を引き起こしたユーザー アクティビティの時間                    | すべてのイベント                               |
    |*影響を受け取ったエンティティ*||
    |  | User                          | DLP 違反を引き起こしたユーザー                                          | すべてのイベント                               |
    |                   | ホスト名                      | DLP 違反が検出されたコンピューターのホスト名              | デバイス イベント                           |
    |                   | IP アドレス                    | コンピューターの IP アドレス                                                  | デバイス イベント                           |
    |                   | ファイル パス                     | 違反に関連するファイルの絶対パス                        | SharePoint イベント、OneDrive イベント、デバイス イベント |
    |                   | 電子メール受信者              | DLP ポリシーに違反した電子メールの受信者                       | Exchange イベント                          |
    |                   | メールの件名                 | DLP ポリシーに違反した電子メールの件名                          | Exchange イベント                          |
    |                   | メールの添付ファイル             | DLP ポリシーに違反した電子メール内の添付ファイルの名前         | Exchange イベント                          |
    |                   | サイト所有者                    | サイト所有者の名前                                                     | SharePoint イベントと OneDrive イベント           |
    |                   | サイトの URL                      | SharePoint または OneDrive サイトの完全な URL                                | SharePoint イベントと OneDrive イベント           |
    |                   | ファイルが作成されました                  | ファイルの作成時間                                                      | SharePoint イベントと OneDrive イベント           |
    |                   | 最後に変更されたファイル            | ファイルの最後の変更時刻                                  | SharePoint イベントと OneDrive イベント           |
    |                   | ファイルのサイズ                     | ファイルのサイズ                                                           | SharePoint イベントと OneDrive イベント           |
    |                   | ファイルの所有者                    | ファイルの所有者                                                          | SharePoint イベントと OneDrive イベント           |
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
