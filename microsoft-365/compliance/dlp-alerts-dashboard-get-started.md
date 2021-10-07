---
title: データ損失防止の警告ダッシュボードを開始する
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
description: データ損失防止ポリシーのアラートの定義と管理について説明します。
ms.openlocfilehash: 601442336cb6ba2a913f3c64eb8345030d0f8209
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60151100"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a>データ損失防止の警告ダッシュボードを開始する

データ損失防止 (DLP) ポリシーは、機密アイテムの意図しない共有を防ぐための保護措置を取る場合があります。 機密性の高いアイテムに対してアクションが実行された場合は、DLP のアラートを構成することで通知を受け取る可能性があります。 この記事では、データ損失防止 (DLP) ポリシーにリンクされているリッチ アラート ポリシーを定義する方法について説明します。 DLP ポリシー違反のアラート、イベント、および関連するメタデータを[](https://compliance.microsoft.com/)表示するには、Microsoft 365 コンプライアンス センターで[DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)アラート管理ダッシュボードを使用する方法について説明します。

DLP アラートを使用する場合は、「データ損失防止アラート ダッシュボードについて [」を確認する必要があります。](dlp-alerts-dashboard-learn.md)

## <a name="before-you-begin"></a>はじめに

開始する前に、必要な前提条件が満たされていることを確認してください。

-   DLP アラート管理ダッシュボードのライセンス
-   アラート構成オプションのライセンス
-   役割

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>DLP アラート管理ダッシュボードのライセンス

DLP の対象となるテナントOffice 365 DLP アラート管理ダッシュボードにアクセスできます。 開始するには、オンライン、オンライン、およびOffice 365の DLP のExchange Online対象SharePoint必要OneDrive for Business。 OFFICE 365 DLP のライセンス要件の詳細については、「どのライセンスがユーザーにサービスの恩恵を受ける権利を提供するか」[を参照してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)。

Teams [DLP](dlp-microsoft-teams.md)の対象となるエンドポイント[DLP](endpoint-dlp-learn-about.md)を使用しているお客様は、DLP アラート管理ダッシュボードにエンドポイント DLP ポリシーアラートと Teams DLP ポリシーアラートを表示します。

コンテンツ **プレビュー機能は** 、次のライセンスでのみ使用できます。

- Microsoft 365 (E5)
- Office 365 (E5)
- 高度なコンプライアンス (E5) アドオン
- Microsoft 365 E5/A5 情報の保護とガバナンス
- Microsft 365 E5/A5 コンプライアンス

### <a name="licensing-for-alert-configuration-options"></a>アラート構成オプションのライセンス

**単** 一イベントアラートの構成: E1、F1、または G1 サブスクリプションまたは E3 または G3 サブスクリプションを持つ組織は、アクティビティが発生する度にアラートがトリガーされる場合にのみアラート ポリシーを作成できます。

**集約アラート構成**: しきい値に基づいて集約アラート ポリシーを構成するには、次のいずれかのライセンス構成が必要です。

- E5 または G5 サブスクリプション
- E1、F1、または G1 サブスクリプション、または次のいずれかの機能を含む E3 または G3 サブスクリプション。
    - Office 365 Advanced Threat Protection プラン 2
    - Microsoft 365 E5 Compliance 
    - Microsoft 365証拠開示と監査アドオン ライセンス

### <a name="roles"></a>役割


DLP アラート管理ダッシュボードを表示する場合、または DLP ポリシーでアラート構成オプションを編集する場合は、次のいずれかの役割グループのメンバーである必要があります。

- コンプライアンス管理者
- コンプライアンス データ管理者
- セキュリティ管理者
- セキュリティ オペレーター
- セキュリティ閲覧者

DLP アラート管理ダッシュボードにアクセスするには、次の情報が必要です。

- アラートの管理

と、次の 2 つの役割のいずれかです。

- DLP コンプライアンス管理
- View-Only DLP コンプライアンス管理

コンテンツ プレビュー機能と一致した機密コンテンツおよびコンテキスト機能にアクセスするには、次のメンバーである必要があります。

- コンテンツ エクスプローラー コンテンツ ビューアーの役割グループ

データ分類コンテンツ ビューアーの役割が事前に割り当てられている。

## <a name="dlp-alert-configuration"></a>DLP アラート構成

DLP ポリシーでアラートを構成する方法については、「データ損失防止の開始場所」 [を参照してください](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)。

### <a name="aggregate-event-alert-configuration"></a>集計イベントアラートの構成

組織に集約アラート構成オプションの[](#licensing-for-alert-configuration-options)ライセンスが設定されている場合は、DLP ポリシーを作成または編集するときにこれらのオプションが表示されます。

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="集約されたアラート構成オプションの対象となるユーザーのインシデント レポートのオプションを示すスクリーンショット。" border="false":::

この構成を使用すると、アクティビティがポリシー条件に一致するか、アクティビティの数に基づいて、または削除されたデータの量に基づいて、特定のしきい値を超えた場合にアラートを生成するポリシーを設定できます。

### <a name="single-event-alert-configuration"></a>単一イベントアラートの構成

組織に単一イベントアラート構成[](#licensing-for-alert-configuration-options)オプションのライセンスが適用されている場合は、DLP ポリシーを作成または編集するときにこれらのオプションが表示されます。 DLP ルールの一致が発生する度に発生するアラートを作成するには、このオプションを使用します。

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="単一イベントアラート構成オプションの対象となるユーザーのインシデント レポートのオプションを示すスクリーンショット。" border="false":::

## <a name="investigate-a-dlp-alert"></a>DLP アラートの調査

DLP アラート管理ダッシュボードを操作するには、次の操作を行います。

1. [データ [損失Microsoft 365 コンプライアンス センター]](https://www.compliance.microsoft.com)**に移動します**。
2. [アラート] **タブを** 選択して、DLP アラート ダッシュボードを表示します。
3. アラートを選択して詳細を表示します。

:::image type="content" source="../media/alert-details.png" alt-text="DLP アラート管理ダッシュボードのアラートの詳細を示すスクリーンショット。" border="false":::

4. [イベント **] タブを** 選択して、アラートに関連付けられているすべてのイベントを表示します。 特定のイベントを選択して、その詳細を表示できます。 使用可能なイベントの詳細の一覧については、「データ損失防止アラート ダッシュボードについて」 [を参照してください](dlp-alerts-dashboard-learn.md)。
5. [詳細 **] を** 選択して、 **アラートの [概要** ] ページを開きます。 概要ページには、次の概要が表示されます。
    1. 何が起こったかの
    1. ポリシーの一致を引き起こしたアクションを実行したユーザー
    1. 一致するポリシーに関する情報など 

6. [イベント] **タブを** 選択して、次の情報にアクセスします。
    1. 関連するコンテンツ
    1. 一致する機密情報の種類
    1. metadata

7. [機密情報 **の種類] タブを** 選択して、コンテンツで検出された機密情報の種類に関する詳細を表示します。 詳細には、信頼度、カウント、および機密情報の種類に一致するコンテンツが含まれます。

8. アラートを調査した後、[概要]タブに戻り、トリアージを管理し、アラートの処理を管理し、コメントを追加できます。

- ワークフロー管理の履歴を表示するには、[管理ログ] **を選択します**。
- アラートに必要なアクションを実行した後、アラートの状態を [解決済み] **に設定します**。

## <a name="see-also"></a>関連項目

- [データ損失防止アラートとアラート ダッシュボードの詳細](dlp-alerts-dashboard-learn.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)