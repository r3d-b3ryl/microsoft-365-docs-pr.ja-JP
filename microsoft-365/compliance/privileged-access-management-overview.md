---
title: 特権アクセス管理
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
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
ms.assetid: ''
description: この記事では、よく寄せられる質問 (Faq) に対する回答を含む、Microsoft 365 での特権アクセス管理の概要について説明します。
ms.openlocfilehash: a1bcf1fbe767b4657be8a8ebcc8bf7b101c498d8
ms.sourcegitcommit: 79a21583a52aedd06317bbcabd8be40663379dec
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/02/2020
ms.locfileid: "48341235"
---
# <a name="privileged-access-management"></a>特権アクセス管理

特権アクセスの管理では、Office 365 の特権的管理タスクを細かくアクセス制限できます。 これは、機密データや重要な構成設定への継続的なアクセス権を持つ既存の特権管理アカウントが使用される違反から組織を保護するために役立ちます。 特権アクセス管理では、ユーザーはジャストインタイムアクセスを要求して、高度に範囲指定された、時間の制限のある承認ワークフローを通じて、昇格された権限のあるタスクを完了させる必要があります。 この構成では、機密性の高いデータや重要な構成の設定を危険にさらすことなくタスクが行えるように、ユーザーに十分なアクセス権が与えられます。 Microsoft 365 で特権アクセス管理を有効にすることで、組織はゼロに立った権限で運用し、管理者アクセスの脆弱性に対する防御層を提供できます。

統合された顧客ロックボックスおよび特権アクセス管理ワークフローの簡単な概要については、この「 [customer のロックボックス」および「privileged access management video](https://go.microsoft.com/fwlink/?linkid=2066800)」を参照してください。

## <a name="layers-of-protection"></a>保護レイヤー

特権アクセス管理は、Microsoft 365 セキュリティアーキテクチャ内の他のデータおよびアクセス機能の保護を補完します。 セキュリティに対する統合および階層化アプローチの一部としての特権アクセス管理を含むセキュリティモデルを使用すると、機密情報の保護を強化し、Microsoft 365 の構成設定を最大限に活用できます。 図に示されているように、特権アクセス管理は、microsoft 365 データのネイティブ暗号化と、Microsoft 365 services の役割ベースのアクセス制御セキュリティモデルによって提供される保護に基づいて構築されています。 [AZURE AD 特権 Id 管理](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)と共に使用する場合、この2つの機能により、さまざまなスコープでジャストインタイムのアクセスを使用してアクセス制御を行うことができます。

![Microsoft 365 での階層型の保護](../media/pam-layered-protection.png)

特権アクセス管理は **タスク** レベルで定義され、スコープが設定されていますが、Azure AD 特権 id 管理は、複数のタスクを実行する機能を使用して、 **役割** レベルで保護を適用します。 Azure AD Privileged Identity Management では、主に AD の役割および役割グループへのアクセスを管理できます。また、Microsoft 365 の特権アクセス管理はタスク レベルにのみ適用されます。

- **既に AZURE AD 特権 Id 管理を使用しているときに、特権アクセス管理を有効にします。** 特権アクセス管理を追加すると、Microsoft 365 データへの特権アクセスのための、より詳細な保護および監査機能が提供されます。

- **Office 365 で既に特権アクセス管理を使用しているときに、AZURE AD 特権 Id 管理を有効にする:**  特権アクセス管理に Azure AD 特権 Id 管理を追加すると、主にユーザーロールまたは id によって定義された Microsoft 365 外部のデータへの特権アクセスを拡張できます。  

## <a name="privileged-access-management-architecture-and-process-flow"></a>特権アクセス管理アーキテクチャとプロセスフロー

次の各プロセスフローは、特権アクセスのアーキテクチャと、それが Microsoft 365 のサブストレート、監査、および Exchange 管理実行空間とどのように連携するかを示しています。

### <a name="step-1-configure-a-privileged-access-policy"></a>手順 1: 特権アクセス ポリシーを構成する

[Microsoft 365 管理センター](https://admin.microsoft.com)または Exchange 管理 PowerShell を使用して特権アクセスポリシーを構成する場合は、ポリシーおよび特権アクセス機能のプロセスおよびポリシー属性を microsoft 365 のサブストレートに定義します。 アクティビティは、セキュリティコンプライアンスセンターに記録され &amp; ます。 ポリシーが有効になり、承認の受信要求を処理する準備が整いました。

![手順 1: ポリシーの作成](../media/pam-step1-policy-creation.jpg)

### <a name="step-2-access-request"></a>手順 2: アクセス要求

[Microsoft 365 管理センター](https://admin.microsoft.com)または Exchange 管理 PowerShell を使用して、ユーザーは昇格されたタスクまたは権限のあるタスクへのアクセスを要求できます。 特権アクセス機能は、構成された特権アクセスポリシーに対して処理するために、Microsoft 365 のサブストレートに要求を送信し、セキュリティコンプライアンスセンターのログにアクティビティを記録し &amp; ます。

![手順 2: アクセス要求](../media/pam-step2-access-request.jpg)

### <a name="step-3-access-approval"></a>手順 3: アクセスの承認

承認要求が生成され、保留中の要求通知が承認者にメールで送信されます。 承認された場合、特権アクセス要求は承認として処理され、タスクを完了する準備が整います。 拒否された場合、タスクはブロックされ、要求者へのアクセスは許可されません。 アクセスの要求者にはメール メッセージで要求の承認または拒否が通知されます。

![手順 3: アクセスの承認](../media/pam-step3-access-approval.jpg)

### <a name="step-4-access-processing"></a>手順 4: アクセスの処理

承認された要求の場合、タスクは Exchange 管理実行空間によって処理されます。 承認は、特権アクセス ポリシーに対してチェックされ、Microsoft 365 サブストレートによって処理されます。 タスクのすべてのアクティビティは、セキュリティコンプライアンスセンターに記録され &amp; ます。

![手順 4: アクセスの処理](../media/pam-step4-access-processing.jpg)

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="what-skus-can-use-privileged-access-in-office-365"></a>Office 365 では、どの Sku で特権アクセスを使用できますか?

特権アクセス管理は、Microsoft 365 および Office 365 のサブスクリプションとアドオンを幅広く選択しているお客様に利用できます。 詳細については [、「特権アクセス管理の概要](privileged-access-management-configuration.md) 」を参照してください。

### <a name="when-will-privileged-access-support-office-365-workloads-beyond-exchange"></a>特権アクセスが Exchange を超えて Office 365 ワークロードをサポートするのはいつですか?

権限のあるアクセス管理は、近日中に他の Office 365 ワークロードで利用可能になります。 詳細については、 [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap) を参照してください。

### <a name="my-organization-needs-more-than-30-privileged-access-policies-will-this-limit-be-increased"></a>自分の組織では30以上の特権アクセスポリシーが必要ですが、この制限は増加しますか?

はい。組織ごとの特権アクセスポリシーの現在の制限は、機能のロードマップにあります。

### <a name="do-i-need-to-be-a-global-admin-to-manage-privileged-access-in-office-365"></a>Office 365 で特権アクセスを管理するには、グローバル管理者である必要がありますか。

いいえ。 Office 365 で特権アクセスを管理するアカウントには、Exchange 役割管理役割が割り当てられている必要があります。 役割管理役割をスタンドアロンのアカウントアクセス許可として構成しない場合は、グローバル管理者の役割に既定でこの役割が含まれ、特権アクセスを管理できます。 承認者のグループに含まれるユーザーは、グローバル管理者である必要がありません。または、PowerShell を使用して要求を確認して承認するための役割管理役割が割り当てられている必要はありません。

### <a name="how-is-privileged-access-management-related-to-customer-lockbox"></a>カスタマーロックボックスに関連する特権アクセス管理の方法

[カスタマーロックボックス](https://docs.microsoft.com/office365/admin/manage/customer-lockbox-requests) Microsoft がデータにアクセスするときに、組織に対してレベルのアクセス制御を許可します。 特権アクセス管理を使用すると、Microsoft 365 のすべての特権タスクに対して、組織内で詳細なアクセス制御を行うことができます。

## <a name="ready-to-get-started"></a>始める準備はいいですか。

[権限のあるアクセス管理の組織の構成を](privileged-access-management-configuration.md)開始します。

## <a name="learn-more"></a>詳細情報

[対話型ガイド: 特権アクセス管理を使用して管理者タスクを監視および制御する](https://content.cloudguides.com/guides/Privileged%20Access%20Management)
