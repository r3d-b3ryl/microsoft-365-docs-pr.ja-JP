---
title: Microsoft Purview データ ライフサイクル管理と Microsoft Purview レコード管理
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection: m365-security-compliance
ms.localizationpriority: high
search.appverid:
- MOE150
- MET150
recommendations: false
description: Microsoft Purview Data ライフサイクル管理と Microsoft Purview レコード管理の機能を実装し、コンプライアンスや規制要件に対応してデータを統制します。
ms.openlocfilehash: d79396b9489bc21f899eaa6ab1ef89b175831095
ms.sourcegitcommit: 45bc65972d4007b2aa7760d4457a0d2699f81926
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/20/2022
ms.locfileid: "64973364"
---
# <a name="govern-your-data-with-microsoft-purview"></a>Microsoft Purview を使用してデータを統制する

[!include[Purview banner](../includes/purview-rebrand-banner.md)]

>*[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

**Microsoft Purview データ ライフサイクル管理** (以前の Microsoft Information Governance) と **Microsoft Purview レコード管理** の機能を使用し、コンプライアンスや規制要件に対応してデータを統制します。

[ライセンスの観点](#licensing-requirements)から見ると、データ ライフサイクル管理とレコード管理の間にはかなりの重複がある可能性があります。 どちらのソリューションも、Microsoft 365 アプリとサービスのデータの保持と削除をサポートしています。

次の図を使用すると、Microsoft Purview コンプライアンス ポータルにそれぞれ独自の構成項目を持つこれらのソリューションで、構成できる主なコンポーネントを特定できます。

![Microsoft Purview を使用してデータを統制するために構成および使用する主なコンポーネント。](../media/govern-your-data.png)

データをセキュリティで保護するには、 「[Microsoft Purview を使用してデータを保護する](information-protection.md)」を参照してください。

## <a name="microsoft-purview-data-lifecycle-management"></a>Microsoft Purview データ ライフサイクル管理

以下のように、必要なものを保持し、不要なものを削除します。
 
|機能|解決される問題|
|:------|:------------|:----------------|
|[Microsoft 365 ワークロードのアイテム保持ポリシー、例外の保持ラベル](retention.md) | メール、ドキュメント、Teams および Yammer メッセージのポリシー管理を使用したコンテンツの保持または削除ができます。 |
|[非アクティブなメールボックス](inactive-mailboxes-in-office-365.md)| 従業員が組織を離れた後もメールボックスのコンテンツを保持して、このコンテンツに管理者、コンプライアンス責任者、レコード マネージャーが引き続きアクセスできるようにします。 |
|[アーカイブ メールボックス](archive-mailboxes.md)| ユーザーに追加のメールボックス ストレージ スペースを提供します。|
|[PST ファイル向けサービスのインポート](importing-pst-files-to-office-365.md)| Exchange Online メールボックスへの PST ファイルの一括インポートをサポートし、コンプライアンスや規制要件に対応してメール メッセージを保持および検索できるようにします。 |

詳細な情報をご希望ですか? 「[データ ライフサイクル管理の詳細](data-lifecycle-management.md)」を参照してください。

これらの機能の一部またはすべての使用を開始する準備はできましたか? 「[データ ライフサイクル管理の使用を開始する](get-started-with-data-lifecycle-management.md)」を参照してください。


## <a name="microsoft-purview-records-management"></a>Microsoft Purview レコード管理

ビジネス、法律、または規制の記録管理要件のために価値の高いアイテムを管理します。

|機能|解決される問題|
|:---------|:---------------------------|
|[ファイル計画](file-plan-manager.md)| 保持ラベルを対話的に作成したり、一括インポートしたり、分析用にエクスポートしたりできます。 ラベルは、ビジネスまたは規制の要件を特定して追跡するのに役立つ、追加の管理情報 (省略可能) をサポートしています。 |
|[個々のアイテムの保持ラベル、アイテム保持ポリシー (ベースライン保持期間に必要な場合)](retention.md)| ラベルは、必要に応じてレコード宣言を使用して手動または自動で適用できる、柔軟な保持期間と削除スケジュールをサポートしています。 |
|[処理確認と処理の証明](disposition.md)| コンテンツを完全に削除する前に手動で確認し、レコードの処理を証明します。|

詳細な情報をご希望ですか? 「[レコード管理の詳細](records-management.md)」を参照してください。

これらの機能の一部またはすべての使用を開始する準備はできましたか? 詳細については、「[レコード管理の概要](get-started-with-records-management.md)」を参照してください。


## <a name="licensing-requirements"></a>ライセンスの要件

ライセンス要件とオプションを理解するには、[Microsoft 365 ライセンス説明書](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)の以下のセクションを参照してください。 
- [Microsoft Purview データ ライフサイクル管理](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-data-lifecycle-management)
- [Microsoft Purview レコード管理](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#microsoft-purview-records-management)

追加のライセンス要件は、ドキュメントの手順に含まれます。 たとえば、メールボックスの管理に特化したライセンスでは、Exchange Online からのライセンスが必要です。