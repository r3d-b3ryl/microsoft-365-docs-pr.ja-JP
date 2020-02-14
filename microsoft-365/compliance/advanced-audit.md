---
title: Microsoft 365 の高度な監査
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Microsoft 365 の高度な監査は、新しい監査機能を提供し、組織におけるフォレンシックおよびコンプライアンスの調査を支援します。
ms.openlocfilehash: e06e7f6330a36c8f98042fcce472b7baf6ef16ff
ms.sourcegitcommit: c2a36b16e354e20db5fd6275175ca856eae55bfc
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2020
ms.locfileid: "41960243"
---
# <a name="advanced-audit-in-microsoft-365"></a>Microsoft 365 の高度な監査

Microsoft 365 の[統合監査機能](search-the-audit-log-in-security-and-compliance.md)を使用すると、組織は Microsoft 365 のさまざまなサービスにわたって、さまざまな種類の監査済みアクティビティを可視化できます。 Microsoft 365 の高度な監査のリリースにより、組織におけるフォレンシックおよびコンプライアンスの調査を支援できる新しい監査機能が追加されました。

> [!NOTE]
> 高度な監査は、Office 365 または Microsoft 365 Enterprise E5 サブスクリプションを持つ組織で利用できます。 さらに、Microsoft 365 E5 コンプライアンス アドオン サブスクリプションは、監査ログの長期保持や価値の高い監査イベントと同様に、高度な監査機能にユーザーごとのライセンスが必要な場合に、ユーザーに割り当てることができます。

この記事では、これらの高度な監査機能の概要について説明します。

## <a name="long-term-retention-of-audit-logs"></a>監査ログの長期保持

高度な監査は、Exchange、SharePoint、および Azure Active Directory の監査レコードを 1 年間保持します。 これは、アクティビティが発生したサービスを示す**ワークロード** プロパティの**Exchange**、**SharePoint**、または **AzureActiveDirectory** の値を含む任意の監査レコードを 1 年間保持する既定の監査ログの保持ポリシーによって実現されます。 これは、フォレンシックまたはコンプライアンスに関する継続的な調査に役立ちます。 詳細については、「監査ログの保持ポリシーの管理」の「[既定の監査ログの保持ポリシー](audit-log-retention-policies.md#default-audit-log-retention-policy)」セクションを参照してください。

## <a name="audit-log-retention-policies"></a>監査ログの保持ポリシー

(前のセクションで説明した) 既定の監査ログの保持ポリシーが適用されていない他のサービスで生成されたすべての監査レコードは、90 日間保持されます。 ただし、カスタマイズした監査ログの保持ポリシーを作成して、最大 1 年間他の監査レコードを保持できます。 次の 1 つ以上の基準に基づいて、監査レコードを保持するポリシーを作成できます。

- 監査されたアクティビティが発生する Microsoft 365 サービス

- 特定の監査済みアクティビティ

- 監査済みアクティビティを実行するユーザー

特定のポリシーが他のポリシーよりも優先されるように、ポリシーおよび優先度のレベルに一致する監査レコードを保持する期間を指定することもできます。 また、組織の一部またはすべてのユーザーに対して Exchange、SharePoint、または Azure Active Directory 監査レコードを 1 年未満で保持する必要がある場合は、カスタム監査ログの保持ポリシーが既定の監査保持ポリシーよりも優先されます。 詳細については、「[監査ログ保持ポリシーを管理する](audit-log-retention-policies.md)」を参照してください。

## <a name="high-value-audit-events"></a>重要な監査イベント

セキュリティ関連の重要な監査イベントおよびコンプライアンス関連の監査イベントは、違反の可能性やその他のフォレンジック調査の調査に役立つイベントです。 リリースする最初のそのような重要なイベントは、*MailItemsAccessed* メールボックスの監査イベントです。 このイベントは、メール プロトコルとクライアントがメール データにアクセスしたときにトリガーされます。 MailItemsAccessed イベントは、調査者がデータ違反を識別し、侵害された可能性があるメッセージの範囲を特定するのに役立ちます。 攻撃者がメール メッセージにアクセスすると、MailItemsAccessed イベントは、実際に読み取られたことを示す明示的な信号がない場合でもトリガーされます (つまり、バインドや同期などのアクセスの種類が監査レコードに記録されます)。

新しい MailItemsAccessed メールボックス アクションは、Exchange Online のメールボックスの監査ログインの MessageBind を置き換え、次の改良点を提供します。

- MessageBind は、AuditAdmin ユーザー ログインの種類に対してのみ構成でき、委任または所有者のアクションには適用されません。 MailItemsAccessed は、すべてのログインの種類に適用されます。

- MessageBind は、メール クライアントによるアクセスのみを対象としています。 同期アクティビティには適用されませんでした。 MailItemsAccessed イベントは、バインド アクセスの種類と同期アクセスの種類の両方によってトリガーされます。

- MessageBind アクションによって、同じメール メッセージにアクセスしたときに複数の監査レコードが作成され、「ノイズ」が監査されます。 一方、MailItemsAccessed イベントは、少数の監査レコードに集約されます。

メールボックスの監査ログインの詳細については、「[メールボックスの監査を管理する](enable-mailbox-auditing.md)」を参照してください。

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Office 365 管理アクティビティ API への高帯域幅アクセス

Office 365 管理アクティビティ API を使用して監査ログにアクセスする組織は、発行者レベルの調整制限により制限されていました。 つまり、発行者が複数のお客様に代わってデータをプルする場合、制限はそれらすべてのお客様で共有されていました。

高度な監査のリリースにより、発行者レベルの制限からテナント レベルの制限に移行しています。 その結果、各組織は、監査データにアクセスするために独自に完全に割り当てられた帯域幅を取得します。 帯域幅は静的な定義済みの制限ではありませんが、組織内のシート数などの要因の組み合わせでモデル化され、E5 組織は E5 以外よりも多くの帯域幅を利用できます。

すべての組織には、最初に 1 分あたり 2,000 件の要求のベースラインが割り当てられます。 この制限は、組織のシート数とライセンス サブスクリプションに応じて動的に増加します。 E5 組織は、E5 以外の組織の約 2 倍の帯域幅を利用できます。 また、サービスの正常性を保護するために、最大帯域幅の上限も設定されます。

詳細については、「[Office 365 管理アクティビティ API リファレンス](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)」の「API 調整」のセクションを参照してください。
