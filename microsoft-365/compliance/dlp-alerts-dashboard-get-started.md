---
title: DLP アラート ダッシュボードの概要
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
description: データ損失防止ポリシーのアラートの定義と管理を開始します。
ms.openlocfilehash: de980fadbc6b6091a0257c032dacab4220704f62
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66625459"
---
# <a name="get-started-with-the-data-loss-prevention-alerts-dashboard"></a>データ損失防止アラート ダッシュボードの概要

Microsoft Purview データ損失防止 (DLP) ポリシーは、機密アイテムの意図しない共有を防ぐために保護アクションを実行できます。 機密アイテムに対してアクションが実行されると、DLP のアラートを構成することで通知を受け取ることができます。 この記事では、データ損失防止 (DLP) ポリシーにリンクされたリッチ アラート ポリシーを定義する方法について説明します。 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a>の [DLP アラート管理ダッシュボード](https://compliance.microsoft.com/datalossprevention?viewid=dlpalerts)を使用して、DLP ポリシー違反のアラート、イベント、および関連メタデータを表示する方法について説明します。

DLP アラートを使用する場合は、[データ損失防止アラートダッシュボードの詳細を](dlp-alerts-dashboard-learn.md)確認する必要があります

## <a name="before-you-begin"></a>はじめに

開始する前に、必要な前提条件があることを確認します。

-   DLP アラート管理ダッシュボードのライセンス
-   アラート構成オプションのライセンス
-   役割

### <a name="licensing-for-the-dlp-alert-management-dashboard"></a>DLP アラート管理ダッシュボードのライセンス

DLP の対象となるすべてのテナントは、DLP アラート管理ダッシュボードにアクセスできます。 作業を開始するには、Exchange Online、SharePoint Online、およびOneDrive for Businessの Microsoft Purview DLP の対象となる必要があります。 DLP のライセンス要件の詳細については、「 [ユーザーがサービスを利用する権限を提供するライセンスはどれですか?」を](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#which-licenses-provide-the-rights-for-a-user-to-benefit-from-the-service-16)参照してください。

Teams DLP の対象となる [エンドポイント DLP](endpoint-dlp-learn-about.md) を使用しているお客様は、 [エンドポイント](dlp-microsoft-teams.md) DLP ポリシー アラートと Teams DLP ポリシー アラートが DLP アラート管理ダッシュボードに表示されます。

**コンテンツ プレビュー** 機能は、次のライセンスでのみ使用できます。

- Microsoft 365 (E5)
- Office 365 (E5)
- 高度なコンプライアンス (E5) アドオン
- Microsoft 365 E5/A5 情報の保護とガバナンス
- Microsoft 365 E5/A5 コンプライアンス

### <a name="licensing-for-alert-configuration-options"></a>アラート構成オプションのライセンス

**単一イベント アラート構成**: E1、F1、または G1 サブスクリプションまたは E3 または G3 サブスクリプションを持つ組織は、アクティビティが発生するたびにアラートがトリガーされる場合にのみアラート ポリシーを作成できます。

**集計アラート構成**: しきい値に基づいてアラート ポリシーの集計を構成するには、次のいずれかのライセンス構成を行う必要があります。

- E5 または G5 サブスクリプション
- E1、F1、または G1 サブスクリプション、または次のいずれかの機能を含む E3 または G3 サブスクリプション。
    - Office 365 Advanced Threat Protection プラン 2
    - Microsoft 365 E5 Compliance 
    - Microsoft 365 電子情報開示および監査アドオン ライセンス

### <a name="roles"></a>役割

DLP アラート管理ダッシュボードを表示する場合、または DLP ポリシーでアラート構成オプションを編集する場合は、次のいずれかのロール グループのメンバーである必要があります。

- コンプライアンス管理者
- コンプライアンス データ管理者
- セキュリティ管理者
- セキュリティ オペレーター
- セキュリティ閲覧者

DLP アラート管理ダッシュボードにアクセスするには、次のものが必要です。

- アラートの管理

と次の 2 つのロールのいずれかです。

- DLP コンプライアンス管理
- 表示専用の DLP コンプライアンス管理

コンテンツ プレビュー機能と一致する機密コンテンツとコンテキスト機能にアクセスするには、次のメンバーである必要があります。

- Content Explorer コンテンツ ビューアーの役割グループ

には、データ分類コンテンツ ビューアー ロールが事前に割り当てられています。

### <a name="roles-and-role-groups-in-preview"></a>プレビュー段階の [役割と役割グループ]

プレビューには、アクセス制御を微調整するためにテストできる役割と役割グループがあります。

プレビュー段階の該当する役割の一覧を次に示します。 詳細については、「[セキュリティとコンプライアンス センターの役割](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#roles-in-the-security--compliance-center)」を参照してください。

- Information Protection 管理者
- Information Protection アナリスト
- Information Protection 調査員
- Information Protection 閲覧者

プレビュー段階の該当する役割グループの一覧を次に示します。 詳細については、「[セキュリティ/コンプライアンス センターの役割グループ](../security/office-365-security/permissions-in-the-security-and-compliance-center.md#role-groups-in-the-security--compliance-center)」を参照してください。

- 情報保護
- Information Protection レベル
- Information Protection アナリスト
- Information Protection 調査担当者
- Information Protection 閲覧者

## <a name="dlp-alert-configuration"></a>DLP アラートの構成

DLP ポリシーでアラートを構成する方法については、「 [データ損失防止の概要」を](create-test-tune-dlp-policy.md#where-to-start-with-data-loss-prevention)参照してください。

> [!IMPORTANT]
> 組織は、ログ保持ポリシーの構成を監査して、アラートがコンソールに表示される期間を制御します。 詳細については、「 [監査ログ保持ポリシーを管理](audit-log-retention-policies.md#manage-audit-log-retention-policies) する」を参照してください。

### <a name="aggregate-event-alert-configuration"></a>イベント アラートの構成を集計する

[組織が集計されたアラート構成オプション](#licensing-for-alert-configuration-options)のライセンスを取得している場合は、DLP ポリシーを作成または編集するときにこれらのオプションが表示されます。

:::image type="content" source="../media/incident-reports-options-aggregated-alerts.png" alt-text="集計されたアラート構成オプションの対象となるユーザーのインシデント レポートのオプションを示すスクリーンショット。" border="false":::

この構成を使用すると、アクティビティがポリシー条件と一致するか、アクティビティの数または流出データの量に基づいて、特定のしきい値を超えたときに毎回アラートを生成するポリシーを設定できます。

### <a name="single-event-alert-configuration"></a>単一イベント アラートの構成

[組織がシングルイベント アラート構成オプション](#licensing-for-alert-configuration-options)のライセンスを取得している場合は、DLP ポリシーを作成または編集するときにこれらのオプションが表示されます。 DLP ルールの一致が発生するたびに発生するアラートを作成するには、このオプションを使用します。

:::image type="content" source="../media/incident-reports-options-single-event-alerts.png" alt-text="単一イベント アラート構成オプションの対象となるユーザーのインシデント レポートのオプションを示すスクリーンショット。" border="false":::

## <a name="investigate-a-dlp-alert"></a>DLP アラートを調査する

DLP アラート管理ダッシュボードを操作するには、

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft Purview コンプライアンス ポータル</a>で、**データ損失防止** に移動します。
2. [ **アラート** ] タブを選択して、DLP アラート ダッシュボードを表示します。
3. アラートを選択して詳細を表示します。

:::image type="content" source="../media/alert-details.png" alt-text="DLP アラート管理ダッシュボードのアラートの詳細を示すスクリーンショット。" border="false":::

4. [ **イベント** ] タブを選択すると、アラートに関連付けられているすべてのイベントが表示されます。 特定のイベントを選択してその詳細を表示できます。 使用可能なイベントの詳細の一覧については、「 [データ損失防止アラート ダッシュボードについて学習する」](dlp-alerts-dashboard-learn.md)を参照してください。
5. **[詳細]** を選択して、アラートの **[概要]** ページを開きます。 概要ページには、次の概要が表示されます。
    1. 何が起こったのか
    1. ポリシー一致の原因となったアクションを実行したユーザー
    1. 一致したポリシーに関する情報など 

6. [ **イベント** ] タブを選択して、次の情報にアクセスします。
    1. 関連するコンテンツ
    1. 一致する機密情報の種類
    1. metadata

7. [ **機密情報の種類** ] タブを選択すると、コンテンツで検出された機密情報の種類に関する詳細が表示されます。 詳細には、信頼度、数、および機密情報の種類に一致するコンテンツが含まれます。

8. アラートを調査したら、[ **概要** ] タブに戻り、トリアージを管理し、アラートの処理を管理し、コメントを追加できます。

- ワークフロー管理の履歴を表示するには、[ **管理ログ**] を選択します。
- アラートに必要なアクションを実行した後、アラートの状態を **解決済み** に設定します。

## <a name="see-also"></a>関連項目

- [データ損失防止アラートとアラート ダッシュボードについて学習する](dlp-alerts-dashboard-learn.md)
- [DLP ポリシーの作成、テスト、調整](create-test-tune-dlp-policy.md)
