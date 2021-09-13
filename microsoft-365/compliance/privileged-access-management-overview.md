---
title: 特権アクセス管理の詳細
description: この記事では、よく寄せられる質問 (FAQ) に対する回答Microsoft 365の特権アクセス管理の概要について説明します。
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
f1.keywords:
- NOCSH
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.openlocfilehash: e66f9133959ce7f09915361e7583ae809e33647e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221154"
---
# <a name="learn-about-privileged-access-management"></a>特権アクセス管理の詳細

特権アクセスの管理では、Office 365 の特権的管理タスクを細かくアクセス制限できます。 これは、機密データや重要な構成設定への継続的なアクセス権を持つ既存の特権管理アカウントが使用される違反から組織を保護するために役立ちます。 特権アクセス管理では、ユーザーが Just-In-Time のアクセスを要求し、広範囲で時間に制約がある承認ワークフローを介して、昇格した特権タスクを完了する必要があります。 この構成では、機密性の高いデータや重要な構成の設定を危険にさらすことなくタスクが行えるように、ユーザーに十分なアクセス権が与えられます。 特権アクセス管理を Microsoft 365有効にすると、組織はゼロの特権で動作し、永続的な管理アクセスの脆弱性に対する防御層を提供できます。

統合された Customer Lockbox と特権アクセス管理ワークフローの概要については、このカスタマー ロックボックスと特権アクセス管理ビデオ [を参照してください](https://go.microsoft.com/fwlink/?linkid=2066800)。

## <a name="layers-of-protection"></a>保護レイヤー

特権アクセス管理は、Microsoft 365 セキュリティ アーキテクチャ内の他のデータおよびアクセス機能保護を補完します。 セキュリティへの統合および階層化アプローチの一部として特権アクセス管理を含めると、機密情報と Microsoft 365 の構成設定の保護を最大化するセキュリティ モデルが実現されます。 図に示すように、特権アクセス管理は、Microsoft 365 データのネイティブ暗号化と Microsoft 365 サービスの役割ベースのアクセス制御セキュリティ モデルで提供される保護に基づいて構築されています。 Azure AD Privileged Identity Management[と](/azure/active-directory/active-directory-privileged-identity-management-configure)一緒に使用する場合、これらの 2 つの機能は、さまざまなスコープで Just-in-time アクセスを使用してアクセス制御を提供します。

![Microsoft 365 のレイヤー Microsoft 365。](../media/pam-layered-protection.png)

特権アクセス管理はタスク レベルで定義およびスコープ設定され、Azure AD Privileged Identity Management は複数のタスクを実行する機能を持つロール レベルで保護を適用します。 Azure AD Privileged Identity Management では、主に AD の役割および役割グループへのアクセスを管理できます。また、Microsoft 365 の特権アクセス管理はタスク レベルにのみ適用されます。

- **Azure サーバーを既に使用している間に特権アクセスAD Privileged Identity Management。** 特権アクセス管理を追加すると、データへの特権アクセスに対する保護と監査機能の別の詳細な層Microsoft 365します。

- **Azure AD Privileged Identity Managementを有効にし、** 既に特権アクセス管理を使用Office 365。 Azure AD Privileged Identity Managementを特権アクセス管理に追加すると、主にユーザーの役割または ID によって定義Microsoft 365外部のデータへの特権アクセスを拡張できます。  

## <a name="privileged-access-management-architecture-and-process-flow"></a>特権アクセス管理アーキテクチャとプロセス フロー

次の各プロセス フローでは、特権アクセスのアーキテクチャと、Microsoft 365 の基体、監査、および Exchange 管理の実行空間とのやり取りについて説明します。

### <a name="step-1-configure-a-privileged-access-policy"></a>手順 1: 特権アクセス ポリシーを構成する

Microsoft 365 管理センター または[Exchange](https://admin.microsoft.com) Management PowerShell を使用して特権アクセス ポリシーを構成する場合は、ポリシーと特権アクセス機能プロセスとポリシー属性を Microsoft 365 基板に定義します。 アクティビティはセキュリティ コンプライアンス センターに &amp; 記録されます。 ポリシーが有効になり、承認の受信要求を処理する準備が整いました。

![手順 1: ポリシーの作成。](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>手順 2: アクセス要求

管理者または[Microsoft 365 管理センター](https://admin.microsoft.com)管理 PowerShell で、ユーザーは管理者特権Exchangeタスクへのアクセスを要求できます。 特権アクセス機能は、構成された特権アクセス ポリシーに対して処理Microsoft 365要求を送信し、セキュリティ コンプライアンス センター ログにアクティビティを &amp; 記録します。

![手順 2: アクセス要求。](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>手順 3: アクセスの承認

承認要求が生成され、保留中の要求通知が承認者にメールで送信されます。 承認された場合、特権アクセス要求は承認として処理され、タスクを完了する準備が整います。 拒否された場合、タスクはブロックされ、要求者へのアクセスは許可されません。 アクセスの要求者にはメール メッセージで要求の承認または拒否が通知されます。

![手順 3: 承認にアクセスします。](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>手順 4: アクセスの処理

承認された要求の場合、タスクは Exchange 管理実行空間によって処理されます。 承認は、特権アクセス ポリシーに対してチェックされ、Microsoft 365 サブストレートによって処理されます。 タスクのすべてのアクティビティがセキュリティ コンプライアンス センターに &amp; 記録されます。

![手順 4: アクセス処理。](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>どの SKU で特権アクセスを使用できるかOffice 365。

特権アクセス管理は、サブスクリプションとアドオンのMicrosoft 365およびOffice 365に利用できます。 詳細については [、「特権アクセス管理の使用を開始する」](privileged-access-management-configuration.md) を参照してください。

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>特権アクセスは、ユーザー以外のOffice 365をサポートExchange?

特権アクセス管理は、他のワークロードですぐにOffice 365利用できます。 詳細については[、「Microsoft 365ロードマップ](https://www.microsoft.com/microsoft-365/roadmap)」を参照してください。

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>組織には 30 以上の特権アクセス ポリシーが必要ですが、この制限は増えますか?

はい、組織ごとに 30 の特権アクセス ポリシーの現在の制限を引き上げることは、機能ロードマップにあります。

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>特権アクセスを管理するには、グローバル管理者である必要Office 365?

いいえ、管理者は、Exchangeの特権アクセスを管理するアカウントに割り当てられた役割の管理役割Office 365。 役割管理役割をスタンドアロン アカウントアクセス許可として構成しない場合、グローバル管理者ロールには既定でこの役割が含まれます。特権アクセスを管理できます。 承認者のグループに含まれるユーザーは、グローバル管理者である必要や、PowerShell を使用して要求を確認および承認するために役割管理役割を割り当てる必要はありません。

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>特権アクセス管理は、Customer Lockbox に関連する方法を説明します。

[顧客ロックボックスを使用](/office365/admin/manage/customer-lockbox-requests) すると、Microsoft がデータにアクセスするときに、組織のアクセス制御レベルを使用できます。 特権アクセス管理を使用すると、すべての権限を持つすべてのタスクに対して組織内Microsoft 365アクセス制御が可能になります。

## <a name="ready-to-get-started"></a>始める準備はいいですか。

特権 [アクセス管理用の組織の構成を開始します](privileged-access-management-configuration.md)。

## <a name="learn-more"></a>詳細情報

[対話型ガイド: 特権アクセス管理を使用して管理者タスクを監視および制御する](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
