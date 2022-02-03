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
- admindeeplinkCOMPLIANCE
description: データ損失防止ポリシーのアラートの定義と管理について説明します。
ms.openlocfilehash: d295a04c27231b937ca552feb06628f857528e34
ms.sourcegitcommit: bae72428d229827cba4c807d9cd362417afbcccb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/02/2022
ms.locfileid: "62321593"
---
# <a name="get-started-with-the-data-loss-prevention-alert-dashboard"></a>データ損失防止の警告ダッシュボードを開始する

データ損失防止 (DLP) ポリシーは、機密アイテムの意図しない共有を防ぐための保護措置を取る場合があります。 機密性の高いアイテムに対してアクションが実行された場合は、DLP のアラートを構成することで通知を受け取る可能性があります。 この記事では、データ損失防止 (DLP) ポリシーにリンクされているリッチ アラート ポリシーを定義する方法について説明します。 DLP ポリシー違反のアラート、イベント、および<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">関連</a>するメタデータを表示するには、Microsoft 365 コンプライアンス センターで [DLP](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts) アラート管理ダッシュボードを使用する方法が表示されます。

DLP アラートを使用する場合は、「データ損失防止アラート ダッシュボードについて [」を確認する必要があります。](dlp-alerts-dashboard-learn.md)

## <a name="before-you-begin"></a>始める前に

開始する前に、必要な前提条件が満たされていることを確認してください。

-   DLP アラート管理ダッシュボードのライセンス
-   アラート構成オプションのライセンス
-   役割

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>DLP アラート管理ダッシュボードのライセンス

DLP の対象となるテナントOffice 365 DLP アラート管理ダッシュボードにアクセスできます。 開始するには、オンライン、オンライン、およびOffice 365の DLP のExchange Online対象SharePoint必要OneDrive for Business。 DLP のライセンス要件の詳細については、「Office 365サービスを利用する権限をユーザーに提供するライセンス」[を参照してください](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)。

エンドポイント DLP の対象[となるエンドポイント DLP](endpoint-dlp-learn-about.md) をTeams[、DLP](dlp-microsoft-teams.md) アラート管理ダッシュボードにエンドポイント DLP ポリシー Teams情報漏えい対策ポリシーアラートが表示されます。

コンテンツ **プレビュー機能は** 、次のライセンスでのみ使用できます。

- Microsoft 365 (E5)
- Office 365 (E5)
- 高度なコンプライアンス (E5) アドオン
- Microsoft 365 E5/A5 情報の保護とガバナンス
- Microsoft 365 E5/A5 コンプライアンス

### <a name="licensing-for-alert-configuration-options"></a>アラート構成オプションのライセンス

**単** 一イベントアラートの構成: E1、F1、または G1 サブスクリプションまたは E3 または G3 サブスクリプションを持つ組織は、アクティビティが発生する度にアラートがトリガーされる場合にのみ、アラート ポリシーを作成できます。

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

### <a name="roles-and-role-groups-in-preview"></a>プレビュー段階の [役割と役割グループ]

プレビューには、アクセス制御を微調整するためにテストできる役割と役割グループがあります。

プレビュー段階の Microsoft Information Protection (MIP) 役割の一覧を次に示します。 詳細については、「[セキュリティとコンプライアンス センターの役割](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)」を参照してください。

- Information Protection 管理者
- Information Protection アナリスト
- Information Protection 調査員
- Information Protection 閲覧者

プレビュー段階の MIP 役割グループの一覧を次に示します。 詳細については、「[セキュリティとコンプライアンス センターの役割グループ](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#role-groups-in-the-security--compliance-center)」を参照してください。

- 情報保護
- Information Protection レベル
- Information Protection アナリスト
- Information Protection 調査担当者
- Information Protection 閲覧者

## <a name="dlp-alert-configuration"></a>DLP アラート構成

DLP ポリシーでアラートを構成する方法については、「データ損失防止の開始場所 [」を参照してください](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)。

> [!IMPORTANT]
> 組織は、ログ保持ポリシーの構成を監査し、コンソールにアラートが表示される期間を制御します。 詳細については、「 [監査ログ保持ポリシーの管理](audit-log-retention-policies.md#manage-audit-log-retention-policies) 」を参照してください。

### <a name="aggregate-event-alert-configuration"></a>集計イベントアラートの構成

組織に集約アラート構成オプションの[](#licensing-for-alert-configuration-options)ライセンスが適用されている場合は、DLP ポリシーを作成または編集するときにこれらのオプションが表示されます。

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="集約されたアラート構成オプションの対象となるユーザーのインシデント レポートのオプションを示すスクリーンショット。" border="false":::

この構成を使用すると、アクティビティがポリシー条件に一致するか、アクティビティの数に基づいて、または削除されたデータの量に基づいて、特定のしきい値を超えた場合にアラートを生成するポリシーを設定できます。

### <a name="single-event-alert-configuration"></a>単一イベントアラートの構成

組織に単一イベント通知構成[](#licensing-for-alert-configuration-options)オプションのライセンスが適用されている場合は、DLP ポリシーを作成または編集するときにこれらのオプションが表示されます。 DLP ルールの一致が発生する度に発生するアラートを作成するには、このオプションを使用します。

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="単一イベントアラート構成オプションの対象となるユーザーのインシデント レポートのオプションを示すスクリーンショット。" border="false":::

## <a name="investigate-a-dlp-alert"></a>DLP アラートの調査

DLP アラート管理ダッシュボードを操作するには、次の操作を行います。

1. [データ <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 コンプライアンス センター</a>] **に移動します**。
2. [アラート] **タブを** 選択して、DLP アラート ダッシュボードを表示します。
3. アラートを選択して詳細を表示します。

:::image type="content" source="../media/alert-details.png" alt-text="DLP アラート管理ダッシュボードのアラートの詳細を示すスクリーンショット。" border="false":::

4. [イベント **] タブを** 選択して、アラートに関連付けられているすべてのイベントを表示します。 特定のイベントを選択して、その詳細を表示できます。 使用可能なイベントの詳細の一覧については、「データ損失防止アラート ダッシュボードについて [」を参照してください](dlp-alerts-dashboard-learn.md)。
5. [詳細 **] を** 選択して、 **アラートの [概要** ] ページを開きます。 概要ページには、次の概要が表示されます。
    1. 何が起こったかの
    1. ポリシーの一致を引き起こしたアクションを実行したユーザー
    1. 一致するポリシーに関する情報など 

6. [イベント] **タブを** 選択して、次の情報にアクセスします。
    1. 関連するコンテンツ
    1. 一致する機密情報の種類
    1. metadata

7. [機密情報 **の種類] タブを** 選択して、コンテンツで検出された機密情報の種類に関する詳細を表示します。 詳細には、信頼度、カウント、および機密情報の種類に一致するコンテンツが含まれます。

8. アラートを調査した後、[概要] タブに戻り、トリアージを管理し、アラートの処理を管理し、コメントを追加できます。

- ワークフロー管理の履歴を表示するには、[管理ログ] **を選択します**。
- アラートに必要なアクションを実行した後、アラートの状態を [解決済み] **に設定します**。

## <a name="see-also"></a>関連項目

- [データ損失防止アラートとアラート ダッシュボードの詳細](dlp-alerts-dashboard-learn.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
