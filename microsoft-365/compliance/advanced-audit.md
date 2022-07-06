---
title: Microsoft Purview 監査 (プレミアム)
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-audit
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft Purview 監査 (プレミアム) では、組織におけるフォレンシックおよびコンプライアンスの調査に役立つ新しい監査機能を提供します。
ms.openlocfilehash: 3f81daf8cafe2f1fa3955dbc175d024e0e9b24ef
ms.sourcegitcommit: c29fc9d7477c3985d02d7a956a9f4b311c4d9c76
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/06/2022
ms.locfileid: "66642308"
---
# <a name="microsoft-purview-audit-premium"></a>Microsoft Purview 監査 (プレミアム)

> [!TIP]
> *9 つの Microsoft Purview ソリューションすべてのプレミアム バージョンを無料で試すことができることをご存知ですか?* 90 日間の Purview ソリューション試用版を使用して、堅牢な Purview 機能が組織のコンプライアンス ニーズを満たすのにどのように役立つかを調べてください。 Microsoft 365 E3 および Office 365 E3 のお客様は、[Microsoft Purview コンプライアンス ポータルの試用版ハブ](https://compliance.microsoft.com/trialHorizontalHub?sku=ComplianceE5&ref=DocsRef)から今すぐ開始できます。 [サインアップできるユーザーと試用版の使用条件](compliance-easy-trials.md)の詳細について説明します。

Microsoft Purview の[監査機能](search-the-audit-log-in-security-and-compliance.md)を使用すると、組織は Microsoft 365 のさまざまなサービスにわたって、さまざまな種類の監査済みアクティビティを可視化できます。 Microsoft Purview 監査 (プレミアム) は、調査の実施に必要な監査ログの保持力を拡大することで、組織によるフォレンジックおよびコンプライアンスの調査を支援します。これにより、(Microsoft Purview コンプライアンス ポータルと Office 365 マネージメント アクティビティ API の監査ログの検索を使用することにより) 侵害の範囲の特定に役立つ重要なイベントへのアクセスおよび Office 365 マネージメント アクティビティ API への迅速なアクセスが提供されます。

> [!NOTE]
> 監査 (プレミアム) は、Office 365 E5/A5/G5 または Microsoft 365 Enterprise E5/A5/G5 サブスクリプションを契約している組織に提供されます。 Microsoft 365 E5/A5/G5 コンプライアンスまたは E5/A5/G5 電子情報開示および監査アドオン ライセンスは、監査ログの長期保持や、調査を目的とした監査 (プレミアム) イベント生成などの監査 (プレミアム) 機能のために、ユーザーに割り当てることができます。 ライセンスの詳細については、次をご覧ください。<br/>- [監査 (プレミアム) のライセンスの必要条件](auditing-solutions-overview.md#licensing-requirements)<br/>- [セキュリティとコンプライアンスのための Microsoft 365 ライセンスの要件](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit)。

この記事では、監査 (プレミアム) 機能の概要を説明し、監査 (プレミアム) 用にユーザーを設定する方法を示します。

## <a name="long-term-retention-of-audit-logs"></a>監査ログの長期保持

監査 (プレミアム) では、Exchange、SharePoint、および Azure Active Directory の監査レコードが 1 年間保持されます。 これは、アクティビティが発生したサービスを示す **ワークロード** プロパティの **Exchange**、**SharePoint**、または **AzureActiveDirectory** の値を含む任意の監査レコードを 1 年間保持する既定の監査ログの保持ポリシーによって実現されます。 監査レコードの長期間にわたる保持は、継続的なフォレンジック調査やコンプライアンス調査に役立ちます。 詳細については、「[監査ログの保持ポリシーの管理](audit-log-retention-policies.md#default-audit-log-retention-policy)」の「既定の監査ログの保持ポリシー」セクションを参照してください。

監査 (プレミアム) の 1 年間の保持機能に加えて、監査ログを 10 年間保持する機能もリリースしました。 監査ログを 10 年間保持することで、長期間にわたる調査や、規制上、法律上、および組織内の義務への対応をサポートします。

> [!NOTE]
> 監査ログを 10 年間保持するには、ユーザー毎の追加のアドオン ライセンスが必要です。 このライセンスがユーザーに割り当てられ、適切な 10 年間の監査ログ保持ポリシーがそのユーザーに対して設定されると、そのポリシーの対象の監査ログは以降 10 年間保持されるようになります。このライセンスがユーザーに割り当てられ、適切に 10 年間の監査ログ保持ポリシーが設定されると、そのポリシーが担保する監査ログは以降 10 年間保持されるようになります。 このポリシーは遡及的ではなく、10 年間の監査ログ保持ポリシーが作成される前に生成された監査ログを保持することはできません。 詳細については、この記事の「[監査 (プレミアム) についてよく寄せられる質問](#faqs-for-audit-premium)」セクションを参照してください。

### <a name="audit-log-retention-policies"></a>監査ログの保持ポリシー

(前のセクションで説明した) 既定の監査ログの保持ポリシーが適用されていない他のサービスで生成されたすべての監査レコードは、90 日間保持されます。 ただし、カスタマイズした監査ログの保持ポリシーを作成すれば、最大 10 年間、長期にわたって他の監査レコードを保持できます。 次の 1 つ以上の基準に基づいて、監査レコードを保持するポリシーを作成できます。

- 監査されたアクティビティが発生する Microsoft 365 サービス。

- 特定の監査されたアクティビティ。

- 監査されたアクティビティを実行するユーザー。

特定のポリシーが他のポリシーよりも優先されるように、ポリシーおよび優先度のレベルに一致する監査レコードを保持する期間を指定することもできます。 また、組織の一部またはすべてのユーザーに対して Exchange、SharePoint、Azure Active Directory 監査レコードを 1 年未満 (または 10 年間) で保持する必要がある場合は、カスタム監査ログの保持ポリシーが既定の監査保持ポリシーよりも優先されます。 詳細については、「[監査ログ保持ポリシーを管理する](audit-log-retention-policies.md)」を参照してください。

## <a name="audit-premium-events"></a>監査 (プレミアム) イベント

監査 (プレミアム) は、いつメール項目がアクセスされたか、いつメール項目が返信されたか、または転送されたか、ユーザーがいつ何を Exchange Online や SharePoint Online で検索したかなどの重要なイベントへのアクセスを提供することで、組織によるフォレンジック調査やコンプライアンス調査の実施をサポートします。 これらのイベントは、起こりうる侵害を調査し、侵害の範囲を決定するのに役立ちます。 これらの Exchange と SharePoint のイベントに加えて、その他の Microsoft 365 サービスにも重要なイベントとみなされるイベントがあり、ユーザーが[適切な監査 (プレミアム) ライセンス](auditing-solutions-overview.md#licensing-requirements)に割り当てられることが必要です。 ユーザーがこれらのイベントを実行する場合に監査ログが生成されるために、ユーザーに監査 (プレミアム) ライセンスを割り当てる必要があります。

監査 (プレミアム) は、次のイベントを提供します。

- [MailItemsAccessed](#mailitemsaccessed)

- [Send](#send)

- [SearchQueryInitiatedExchange](#searchqueryinitiatedexchange)

- [SearchQueryInitiatedSharePoint](#searchqueryinitiatedsharepoint)

- [Microsoft 365 のその他の監査 (プレミアム) イベント](#other-audit-premium-events-in-microsoft-365)

### <a name="mailitemsaccessed"></a>MailItemsAccessed

MailItemsAccessed イベントは、メールボックス監査アクションであり、メール データがメール プロトコルやメール クライアントによってアクセスされたときにトリガーされます。 イベントは、調査者がデータ違反を識別し、侵害された可能性があるメッセージの範囲を特定するのに役立ちます。 攻撃者がメール メッセージにアクセスすると、MailItemsAccessed アクションは、メッセージが実際に読み取られたことを示す明示的な信号がない場合でもトリガーされます (つまり、バインドや同期などのアクセスの種類が監査レコードに記録されます)。

MailItemsAccessed イベントは、Exchange Online のメールボックスの監査ログの MessageBind を置き換え、次の改善点を提供します。

- MessageBind は、AuditAdmin ユーザーのログインの種類に対してのみ構成でき、委任または所有者のアクションには適用されませんでした。MailItemsAccessed は、すべてのログインの種類に適用されます。

- MessageBind は、メール クライアントによるアクセスのみを対象としています。 同期アクティビティには適用されませんでした。 MailItemsAccessed イベントは、バインド アクセスの種類と同期アクセスの種類の両方によってトリガーされます。

- MessageBind アクションによって、同じメール メッセージにアクセスしたときに複数の監査レコードが作成され、「ノイズ」が監査されます。一方、MailItemsAccessed イベントは、少数の監査レコードに集約されます。

MailItemsAccessed アクティビティの監査レコードの詳細については、「[監査 (プレミアム) を使用して、侵害されたアカウントを調査する](mailitemsaccessed-forensics-investigations.md)」を参照してください。

MailItemsAccessed 監査レコードを検索するには、コンプライアンス ポータル内の [監査ログ検索ツール](search-the-audit-log-in-security-and-compliance.md)の **Exchange メールボックス アクティビティ** ドロップダウン リストで **メールボックス アイテムへのアクセス** アクティビティを検索できます。

![監査ログ検索ツールで MailItemsAccessed アクションを検索する。](../media/AdvAudit_MailItemsAccessed.png)

Exchange Online PowerShell で [Search-UnifiedAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-unifiedauditlog) または [Search-MailboxAuditLog -Operations MailItemsAccessed](/powershell/module/exchange/search-mailboxauditlog) コマンドを実行することもできます。

### <a name="send"></a>Send

Send イベントもメールボックス監査アクションであり、ユーザーが次のアクションのいずれかを実行したときにトリガーされます。

- メール メッセージの送信

- メール メッセージへの返信

- メール メッセージの転送

調査担当者は Send イベントを使用して、侵害されたアカウントから送信されたメールを特定することができます。 Send イベントの監査レコードには、メッセージが送信された日時、InternetMessage ID、件名、メッセージに添付ファイルが含まれているかどうかなどのメッセージに関連する情報が含まれています。 この監査情報は、調査担当者が侵害されたアカウントから送信された、または攻撃者によって送信されたメール メッセージに関連する情報を特定するのに役立ちます。 さらに、調査担当者は Microsoft 365 の電子情報開示ツールを使用して (件名やメッセージ ID を使用して) メッセージを検索し、メッセージの送信先である受信者と送信されたメッセージの実際の内容を特定することができます。

Send 監査レコードを検索するには、コンプライアンス ポータル内の [監査ログ検索ツール](search-the-audit-log-in-security-and-compliance.md)の **Exchange メールボックス アクティビティ** ドロップダウン リストで **送信済みメッセージ** アクティビティを検索できます。

![監査ログ検索ツールでの送信済みメッセージ アクションの検索。](../media/AdvAudit_SentMessage.png)

Exchange Online PowerShell で [Search-UnifiedAuditLog -Operations Send](/powershell/module/exchange/search-unifiedauditlog) または [Search-MailboxAuditLog -Operations Send](/powershell/module/exchange/search-mailboxauditlog) コマンドを実行することもできます。

### <a name="searchqueryinitiatedexchange"></a>SearchQueryInitiatedExchange

SearchQueryInitiatedExchange イベントは、ユーザーが Outlook を使用してメールボックス内のアイテムを検索するときにトリガーされます。 次の Outlook 環境で検索が実行されると、イベントがトリガーされます。

- Outlook (デスクトップ クライアント)

- Outlook on the web (OWA)

- Outlook for iOS

- Outlook for Android

- Windows 10 用メール アプリ

調査担当者は SearchQueryInitiatedExchange イベントを使用し、アカウントを侵害した可能性のある攻撃者がメールボックス内の機密情報を探したり、アクセスしようとしたかどうかを判断することができます。 SearchQueryInitiatedExchange イベントの監査レコードには、検索クエリの実際のテキストなどの情報が含まれています。 監査レコードは、検索が実行された Outlook 環境も示します。 攻撃者が実行した可能性のある検索クエリを調査することで、調査担当者は検索されたメール データの意図をより深く理解することができます。

SearchQueryInitiatedExchange 監査レコードを検索するには、コンプライアンス センター内の [監査ログ検索ツール](search-the-audit-log-in-security-and-compliance.md)の **検索アクティビティ** ドロップダウン リストで **実行されたメール検索** アクティビティを検索できます。

![監査ログ検索ツールでの実行されたメール検索アクションの検索。](../media/AdvAudit_SearchExchange.png)

また、Exchange Online PowerShell で [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](/powershell/module/exchange/search-unifiedauditlog) を実行することもできます。

> [!NOTE]
> 監査ログでこのイベントを検索するには、SearchQueryInitiatedExchange がログに記録されるようにする必要があります。手順については、「[監査 (プレミアム) の設定](set-up-advanced-audit.md#step-2-enable-audit-premium-events)」を参照してください。

### <a name="searchqueryinitiatedsharepoint"></a>SearchQueryInitiatedSharePoint

メールボックス アイテムの検索と同様に、SharePoint 内のアイテムをユーザーが検索すると、SearchQueryInitiatedSharePoint イベントがトリガーされます。 次の種類の SharePoint サイトのルートまたは既定のページで検索が実行されるとイベントがトリガーされます。

- ホーム サイト

- コミュニケーション サイト

- ハブ サイト

- Microsoft Teams に関連付けられているサイト

調査担当者は、SearchQueryInitiatedSharePoint イベントを使用して攻撃者が SharePoint 内の機密情報を見つけようとした (そしてアクセスした可能性がある) かどうかを判断することができます。 SearchQueryInitiatedSharePoint イベントの監査レコードには、検索クエリの実際のテキストも含まれています。 監査レコードには、検索された SharePoint サイトの種類も示されます。 攻撃者が実行した可能性のある検索クエリを調査することで、調査担当者は検索されたファイル データの意図や範囲をより深く理解することができます。

SearchQueryInitiatedSharePoint 監査レコードを検索するには、コンプライアンス センター内の [監査ログ検索ツール](search-the-audit-log-in-security-and-compliance.md)の **検索アクティビティ** ドロップダウン リストで **実行された SharePoint 検索** アクティビティを検索できます。

![監査ログ検索ツールでの実行された SharePoint 検索アクションの検索。](../media/AdvAudit_SearchSharePoint.png)

また、Exchange Online PowerShell で [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](/powershell/module/exchange/search-unifiedauditlog) を実行することもできます。

> [!NOTE]
> 監査ログでこのイベントを検索するには、SearchQueryInitiatedSharePoint がログに記録されるようにする必要があります。手順については、「[監査 (プレミアム) の設定](set-up-advanced-audit.md#step-2-enable-audit-premium-events)」を参照してください。

### <a name="other-audit-premium-events-in-microsoft-365"></a>Microsoft 365 のその他の監査 (プレミアム) イベント

Exchange Online と SharePoint Online のイベントに加えて、その他の Microsoft 365 サービスにもイベントとみなされるイベントがあり、ユーザーに適切な監査 (プレミアム) ライセンスが割り当てられている場合は、ログに記録されます。 次の Microsoft 365 サービスでは、監査 (プレミアム) イベントを提供します。 対応するリンクを選択して、これらのイベントを特定し説明する記事に移動します。

- [Microsoft Forms](search-the-audit-log-in-security-and-compliance.md#microsoft-forms-activities)

- [Microsoft Stream](/stream/audit-logs#actions-logged-in-stream)

- [Microsoft Teams](/microsoftteams/audit-log-events#teams-activities)

- [Yammer](search-the-audit-log-in-security-and-compliance.md#yammer-activities)

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Office 365 管理アクティビティ API への高帯域幅アクセス

Office 365 管理アクティビティ API を使用して監査ログにアクセスする組織は、発行者レベルの調整制限により制限されていました。 つまり、発行者が複数のお客様に代わってデータをプルする場合、制限はそれらすべてのお客様で共有されていました。

監査 (プレミアム) のリリースにより、発行者レベルの制限からテナント レベルの制限に移行します。 その結果、各組織は、監査データにアクセスするために独自に完全に割り当てられた帯域幅を取得します。 帯域幅は静的な定義済みの制限ではありませんが、組織内のシート数などの要因の組み合わせでモデル化され、E5/A5/G5 組織は E5/A5/G5 以外よりも多くの帯域幅を利用できます。

すべての組織には、最初に 1 分あたり 2,000 件の要求のベースラインが割り当てられます。 この制限は、組織のシート数とライセンス サブスクリプションに応じて動的に増加します。 E5/A5/G5 組織は、E5/A5/G5 以外の組織の約 2 倍の帯域幅を利用できます。 また、サービスの正常性を保護するために、最大帯域幅の上限も設定されます。

詳細については、「[Office 365 管理アクティビティ API リファレンス](/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)」の「API 調整」のセクションを参照してください。

## <a name="faqs-for-audit-premium"></a>監査 (プレミアム) の FAQ

**監査 (プレミアム) を利用するには、すべてのユーザーに E5/A5/G5 ライセンスが必要ですか ?**

ユーザー レベルの監査 (プレミアム) 機能を利用するには、ユーザーに E5/A5/G5 ライセンスを割り当てる必要があります。 適切なライセンスをチェックして、ユーザーに機能を公開するための機能がいくつかあります。 たとえば、90 日を超えて適切なライセンスが割り当てられていないユーザーの監査レコードを保持しようとすると、システムはエラー メッセージを返します。

**組織が E5/A5/G5 サブスクリプションを持っている場合、監査 (プレミアム) イベントの監査レコードにアクセスするために何かをする必要はありますか?**

適切な E5/A5/G5 ライセンスの割り当てを受けた対象のお客様とユーザーの場合、(この記事で前述したとおり) SearchQueryInitiatedExchange および SearchQueryInitiatedSharePoint のイベントを有効にすることを除き、監査 (プレミアム) イベントにアクセスするために必要な操作はありません。 監査 (プレミアム) イベントは、E5/A5/G5 ライセンスを持つユーザーに対して、これらのライセンスが割り当てられた後にのみ生成されます。

**監査 (プレミアム) の新しいイベントは、Office 365 マネージメント アクティビティ API で利用できますか?**

はい。適切なライセンスを持つユーザーの監査レコードが生成されている限り、Office 365 マネージメント アクティビティ API を介してこれらのレコードにアクセスできます。

**この機能が一般公開されたときに 10 年間の監査ログ保持ポリシーを作成したものの、必要なアドオン ライセンスが提供される前であった場合、組織の監査ログ データはどうなりますか?**

2020 年の第 4 四半期に機能が一般提供リリースされた後に作成された 10 年間の監査ログ保持ポリシーの対象となる任意の監査ログ データについては、10 年間にわたって保持されます。 これには、必須のアドオン ライセンスが 2021 年 3 月にリリースされて購入可能となった以前に作成された 10 年間の監査ログ保持ポリシーが含まれますす。 ただし、現在は 10 年間の監査ログ保持アドオン ライセンスが提供されているため、10 年間の監査保持ポリシーが適用されている監査データの対象となるすべてのユーザーについて、アドオン ライセンスを購入して割り当てる必要があります。
