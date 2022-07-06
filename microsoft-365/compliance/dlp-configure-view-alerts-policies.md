---
title: DLP ポリシーのアラートを構成して表示する
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
ms.openlocfilehash: 60d5188b9288b1e131e36e145f7abb98a34d5ead
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66627649"
---
# <a name="configure-and-view-alerts-for-data-loss-prevention-polices"></a>データ損失防止ポリシーのアラートを構成して表示する

Microsoft Purview データ損失防止 (DLP) ポリシーは、機密アイテムの意図しない共有を防ぐために保護アクションを実行できます。 機密アイテムに対してアクションが実行されると、DLP のアラートを構成することで通知を受け取ることができます。 この記事では、データ損失防止 (DLP) ポリシーにリンクされたリッチ アラート ポリシーを定義する方法について説明します。 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a>の新しい DLP アラート管理ダッシュボードを使用して、DLP ポリシー違反のアラート、イベント、および関連メタデータを表示する方法について説明します。

## <a name="features"></a>機能

これには、次の機能が含まれます。

-   **DLP アラート管理ダッシュボード**: <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a>では、このダッシュボードには、次のワークロードに適用される DLP ポリシーのアラートが表示されます。

    -   Exchange
    -   SharePoint
    -   OneDrive
    -   Teams
    -   デバイス
-   **高度なアラート構成オプション**: これらのオプションは、DLP ポリシー作成フローの一部です。 これらを使用して、豊富なアラート構成を作成します。 リークされたデータのイベント数やサイズに基づいて、単一イベント アラートまたは集計アラートを作成できます。

## <a name="before-you-begin"></a>はじめに

開始する前に、必要な前提条件があることを確認します。

-   DLP アラート管理ダッシュボードのライセンス
-   アラート構成オプションのライセンス
-   役割

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>DLP アラート管理ダッシュボードのライセンス

Office 365 DLP の対象となるすべてのテナントは、新しい DLP アラート管理ダッシュボードにアクセスできます。 作業を開始するには、Exchange Online、SharePoint Online、およびOneDrive for Businessの DLP をOffice 365する資格があります。 Office 365 DLP のライセンス要件の詳細については、「[ユーザーがサービスを利用する権限を提供するライセンスはどれですか?」を](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)参照してください。

Teams DLP の対象となる [エンドポイント DLP](endpoint-dlp-learn-about.md) を使用しているお客様は、 [エンドポイント](dlp-microsoft-teams.md) DLP ポリシー アラートと Teams DLP ポリシー アラートが DLP アラート管理ダッシュボードに表示されます。

### <a name="licensing-for-alert-configuration-options"></a>アラート構成オプションのライセンス

- **単一イベント アラート構成**: E1、F1、または G1 サブスクリプションまたは E3 または G3 サブスクリプションを持つ組織は、アクティビティが発生するたびにアラートがトリガーされる場合にのみアラート ポリシーを作成できます。
- **集計アラート構成**: しきい値に基づいてアラート ポリシーの集計を構成するには、次のいずれかの構成が必要です。
  - E5 または G5 サブスクリプション
  - E1、F1、または G1 サブスクリプション、または次のいずれかの機能を含む E3 または G3 サブスクリプション。
    - Office 365 Advanced Threat Protection プラン 2
    - Microsoft 365 E5 Compliance 
    - Microsoft 365 電子情報開示および監査アドオン ライセンス

### <a name="roles"></a>役割

DLP アラート管理ダッシュボードを表示する場合、または DLP ポリシーでアラート構成オプションを編集する場合は、次のいずれかのロール グループのメンバーである必要があります。

-   コンプライアンス管理者
-   コンプライアンス データ管理者
-   セキュリティ管理者
-   セキュリティ オペレーター
-   セキュリティ閲覧者

DLP アラート管理ダッシュボードにアクセスするには、アラートの管理ロールと次のいずれかのロールが必要です。

-   DLP コンプライアンス管理
-   表示専用の DLP コンプライアンス管理

## <a name="alert-configuration-experience"></a>アラート構成エクスペリエンス

[集計されたアラート構成オプション](#licensing-for-alert-configuration-options)の対象となる場合は、DLP ポリシー作成エクスペリエンスに次のオプションがインラインで表示されます。

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="集計されたアラート構成オプションの対象となるユーザーのインシデント レポートのオプションを示すスクリーンショット。" border="false":::

この構成では、アラートを生成するポリシーを設定できます。

- アクティビティがポリシー条件と一致するたびに
- 定義されたしきい値が満たされたとき、または超えた場合
- アクティビティの数に基づいて
- 流出したデータの量に基づく

通知メールの大量発生を防ぐために、1 分間の時間枠内で発生し、同じ DLP ルールと同じ場所にあるすべての一致が、同じアラートにグループ化されます。 1 分間の集計時間枠機能は、次の機能で使用できます。 

- E5 または G5 サブスクリプション
- E1、F1、または G1 サブスクリプション、または次のいずれかの機能を含む E3 または G3 サブスクリプション。
    - Office 365 Advanced Threat Protection プラン 2
    - Microsoft 365 E5 Compliance 
    - Microsoft 365 電子情報開示および監査アドオン ライセンス
 
E1、F1、または G1 サブスクリプションまたは E3 または G3 サブスクリプションを持つ組織の場合、集計期間は 15 分です。

## <a name="dlp-alert-management-dashboard"></a>DLP アラート管理ダッシュボード

DLP アラート管理ダッシュボードを操作するには、

1.  <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a>で、**データ損失防止** に移動します。

2.  [ **アラート** ] タブを選択して、DLP アラート ダッシュボードを表示します。

    -   フィルターを選択して、アラートの一覧を絞り込みます。 [ **列のカスタマイズ]** を選択して、表示するプロパティを一覧表示します。 任意の列でアラートを昇順または降順で並べ替えることもできます。
    -   アラートを選択して詳細を表示します。

        :::image type="content" source="../media/alert-details.png" alt-text="DLP アラート管理ダッシュボードのアラートの詳細を示すスクリーンショット。" border="false":::

1.  [ **イベント** ] タブを選択すると、アラートに関連付けられているすべてのイベントが表示されます。 特定のイベントを選択してその詳細を表示できます。 次の表は、イベントの詳細の一部を示しています。
    
    | カテゴリ          | プロパティ名                 | 説明                                                                | 適用可能なイベントの種類                   |
    |-------------------|-------------------------------|----------------------------------------------------------------------------|------------------------------------------|
    |*イベントの詳細*||
    |      | Id                            | イベントに関連付けられた一意の ID                                        | すべてのイベント                               |
    |                   | 場所                      | イベントが検出されたワークロード                                      | すべてのイベント                               |
    |                   | アクティビティの時刻              | DLP 違反の原因となったユーザー アクティビティの時刻                    | すべてのイベント                               |
    |*影響を受けたエンティティ*||
    |  | User                          | DLP 違反を引き起こしたユーザー                                          | すべてのイベント                               |
    |                   | ホスト名                      | DLP 違反が検出されたマシンのホスト名              | デバイス イベント                           |
    |                   | IP アドレス                    | マシンの IP アドレス                                                  | デバイス イベント                           |
    |                   | ファイル パス                     | 違反に関係するファイルの絶対パス                        | SharePoint、OneDrive、および Devices イベント |
    |                   | 電子メール受信者              | DLP ポリシーに違反した電子メールの受信者                       | Exchange イベント                          |
    |                   | メールの件名                 | DLP ポリシーに違反した電子メールの件名                          | Exchange イベント                          |
    |                   | メールの添付ファイル             | DLP ポリシーに違反した電子メール内の添付ファイルの名前         | Exchange イベント                          |
    |                   | サイト所有者                    | サイト所有者の名前                                                     | SharePoint イベントと OneDrive イベント           |
    |                   | サイトの URL                      | SharePoint または OneDrive サイトの完全な URL                                | SharePoint イベントと OneDrive イベント           |
    |                   | ファイルが作成されました                  | ファイルの作成時刻                                                      | SharePoint イベントと OneDrive イベント           |
    |                   | 最後に変更されたファイル            | ファイルの最後の変更時刻                                  | SharePoint イベントと OneDrive イベント           |
    |                   | ファイルのサイズ                     | ファイルのサイズ                                                           | SharePoint イベントと OneDrive イベント           |
    |                   | ファイル所有者                    | ファイルの所有者                                                          | SharePoint イベントと OneDrive イベント           |
    |*ポリシーの詳細*||
    |     | DLP ポリシーの一致            | 一致した DLP ポリシーの名前                                    | すべてのイベント                               |
    |                   | 一致するルール                  | 一致した DLP ポリシー内の DLP ルールの名前                    | すべてのイベント                               |
    |                   | 検出された機密情報の種類 | DLP ポリシーの一部として検出された機密情報の種類 | すべてのイベント                               |
    |                   | 実行された処理                 | 一致する DLP ポリシーの一部として実行されるアクション                          | すべてのイベント                               |
    |                   | ユーザー オーバーロード ポリシー          | ユーザーがポリシー ヒントを使用してポリシーを上書きするかどうか                | すべてのイベント                               |
    |                   | 両端揃えテキストをオーバーライドする   | ポリシー ヒントをオーバーライドするための理由                          | すべてのイベント                               |
    
1.  [ **機密情報の種類** ] タブを選択すると、コンテンツで検出された機密情報の種類に関する詳細が表示されます。 詳細には、信頼度とカウントが含まれます。

2.  アラートを調査したら、[アラートの **管理** ] を選択して状態を変更します (**アクティブ**、 **調査**、 **却下**、解決 **済み**)。 また、コメントを追加し、組織内のユーザーにアラートを割り当てることもできます。

    -   ワークフロー管理の履歴を表示するには、[ **管理ログ**] を選択します。
    -   アラートに必要なアクションを実行した後、アラートの状態を **解決済み** に設定します。
