---
title: Microsoft 365 の Microsoft 情報ガバナンス
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
recommendations: false
description: コンプライアンスや規制の要件を満たすようにデータを管理するには、Microsoft 情報ガバナンス機能を実装します。
ms.openlocfilehash: 75407c8633698d59cf571edcee7e5ed581729bc8a218f5bc45decfe3ac66d307
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53801442"
---
# <a name="microsoft-information-governance-in-microsoft-365"></a>Microsoft 365 の Microsoft 情報ガバナンス

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

Microsoft 情報ガバナンス (MIG と略されることもあります) 機能を使用して、コンプライアンスや規制の要件を満たすようにデータを管理します。

![データを管理する - 情報ガバナンスとレコード管理](../media/information-governance-records-management.png)

データをセキュリティで保護するには、 「[Microsoft 365 の Microsoft Information Protection](information-protection.md)」を参照してください。

データのプライバシー規則を遵守できるよう、安全なアクセス、脅威からの保護、情報の保護、データ ガバナンスなど、Microsoft 365 全体の機能を計画および実装するためのエンド ツー エンドのプロセスがわかるワークフローを設計しました。詳細については、「[Microsoft 365を使用したデータプライバシー規制の情報保護の展開 ](../solutions/information-protection-deploy.md) 」(aka.ms/m365dataprivacy) を参照してください。 

## <a name="information-governance"></a>情報ガバナンス

以下のように、必要なものを保持し、不要なものを削除します。
 
|機能|解決される問題|作業の開始|
|:------|:------------|:--------------------|:-----------------------------|
|[アイテム保持ポリシーと保持ラベル](retention.md)| メール、ドキュメント、インスタント メッセージなどのポリシー管理および削除ワークフローを使用して、コンテンツを保持または削除する <br /><br />シナリオ例: [保持ラベルをコンテンツに自動的に適用する](apply-retention-labels-automatically.md) | [アイテム保持ポリシーおよび保持ラベルの使用を開始する](get-started-with-retention.md)|
|[サービスをインポートする](importing-pst-files-to-office-365.md)| Exchange Online メールボックスに PST ファイルを一括インポートして、コンプライアンスや規制要件に対応してメールメッセージを保持し検索する | [ネットワーク アップロードを使用して、組織の PST ファイルを Microsoft 365 にインポートする](use-network-upload-to-import-pst-files.md)|
|[サードパーティのデータをアーカイブする](archiving-third-party-data.md)| ソーシャル メディア プラットフォーム、インスタント メッセージング プラットフォーム、ドキュメント コラボレーション プラットフォームからサードパーティのデータをインポートし、アーカイブして、コンプライアンス ソリューションを適用する| [サードパーティのコネクタ](archiving-third-party-data.md#third-party-data-connectors)|
|[非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)| 従業員が組織を離れた後にメールボックスのコンテンツを保持する | [非アクティブなメールボックスを作成および管理する](create-and-manage-inactive-mailboxes.md)|

## <a name="records-management"></a>レコード管理

以下のように、法的、ビジネス、または規制上の義務のために価値の高いコンテンツを管理します。

|機能|解決される問題|作業の開始|
|:------|:------------|---------------------|:----------------------------|
|[レコード管理](records-management.md)| レコード宣言、保持、処理により、コンテンツのライフサイクル全体をサポートする、保持スケジュールと要件をファイル計画に組み込んだメールとドキュメント用の単一ソリューション。 <br /><br />シナリオ例: [ レコードの処理](disposition.md#disposition-of-records)|[レコード管理の使用を開始する](get-started-with-records-management.md) |

## <a name="licensing-requirements"></a>ライセンスの要件

Microsoft 情報ガバナンスのライセンス要件は、このページにリストされている各機能のライセンス要件を設定するのではなく、使用するシナリオと機能によって異なります。 ライセンス要件とオプションを理解するには、Microsoft 365 ライセンス ドキュメントの「[情報ガバナンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-governance)」 と 「[レコード管理](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#records-management)」セクションを参照し、関連する PDF または Excel をダウンロードしてください。