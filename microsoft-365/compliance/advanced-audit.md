---
title: Microsoft 365 の高度な監査
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-audit
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 の高度な監査では、組織におけるフォレンシックおよびコンプライアンスの調査に役立つ新しい監査機能を提供します。
ms.openlocfilehash: f265a30a3d43b592a7d297e2137fd6b9ff4acfb4
ms.sourcegitcommit: 8e696c084d097520209c864140af11aa055b979e
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/03/2021
ms.locfileid: "50097153"
---
# <a name="advanced-audit-in-microsoft-365"></a>Microsoft 365 の高度な監査

Microsoft 365 の[統合監査機能](search-the-audit-log-in-security-and-compliance.md)を使用すると、組織は Microsoft 365 のさまざまなサービスにわたって、さまざまな種類の監査済みアクティビティを可視化できます。 高度な監査は、侵害の範囲の決定に役立つ重要なイベントへのアクセスを提供し、Office 365 管理アクティビティ API への迅速なアクセスを提供することで、調査の実施に必要な監査ログの保持を高め、組織によるフォレンジック調査やコンプライアンス調査の実施をサポートします。

> [!NOTE]
> 高度な監査は、Office 365 E5/G5 または Microsoft 365 Enterprise E5/G5のサブスクリプションを持つ組織で利用できます。 さらに、Microsoft 365 E5 コンプライアンス アドオン ライセンスや Microsoft 365 E5 eDiscovery and Audit アドオン ライセンスは、監査ログの長期保持や調査のための重要なイベントへのアクセスと同様に、高度な監査機能にユーザーごとのライセンスが必要な場合に、ユーザーに割り当てることができます。 ライセンスの詳細については、「[セキュリティとコンプライアンスのための Microsoft 365 ライセンス ガイダンス](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#advanced-audit)」を参照してください。

この記事では、高度な監査機能の概要を説明し、高度な監査用にユーザーを設定する方法を示します。

## <a name="long-term-retention-of-audit-logs"></a>監査ログの長期保持

高度な監査では、Exchange、SharePoint、および Azure Active Directory の監査レコードが 1 年間保持されます。 これは、アクティビティが発生したサービスを示す **ワークロード** プロパティの **Exchange**、**SharePoint**、または **AzureActiveDirectory** の値を含む任意の監査レコードを 1 年間保持する既定の監査ログの保持ポリシーによって実現されます。 監査レコードの長期間にわたる保持は、継続的なフォレンジック調査やコンプライアンス調査に役立ちます。 詳細については、「[監査ログの保持ポリシーの管理](audit-log-retention-policies.md#default-audit-log-retention-policy)」の「既定の監査ログの保持ポリシー」セクションを参照してください。

また、監査ログを 10 年間保持する機能もリリースしています。 監査ログを 10 年間保持することで、長期間にわたる調査や、規制、法律、社内の義務への対応をサポートします。

> [!NOTE]
> 監査ログを 10 年間保持するには、追加のアドオン ライセンスが必要です。 この新しいライセンスは、2021 年初頭より利用可能になります。 詳細については、この記事の「[高度な監査についてよく寄せられる質問](#faqs-for-advanced-audit)」セクションを参照してください。

### <a name="audit-log-retention-policies"></a>監査ログの保持ポリシー

(前のセクションで説明した) 既定の監査ログの保持ポリシーが適用されていない他のサービスで生成されたすべての監査レコードは、90 日間保持されます。 ただし、カスタマイズした監査ログの保持ポリシーを作成すれば、最大 10 年間、長期にわたって他の監査レコードを保持できます。 次の 1 つ以上の基準に基づいて、監査レコードを保持するポリシーを作成できます。

- 監査されたアクティビティが発生する Microsoft 365 サービス。

- 特定の監査されたアクティビティ。

- 監査されたアクティビティを実行するユーザー。

特定のポリシーが他のポリシーよりも優先されるように、ポリシーおよび優先度のレベルに一致する監査レコードを保持する期間を指定することもできます。 また、組織の一部またはすべてのユーザーに対して Exchange、SharePoint、Azure Active Directory 監査レコードを 1 年未満 (または 10 年間) で保持する必要がある場合は、カスタム監査ログの保持ポリシーが既定の監査保持ポリシーよりも優先されます。 詳細については、「[監査ログ保持ポリシーを管理する](audit-log-retention-policies.md)」を参照してください。

## <a name="access-to-crucial-events-for-investigations"></a>調査のための重要なイベントへのアクセス

高度な監査は、いつメール項目がアクセスされたか、いつメール項目が返信されたか、または転送されたか、ユーザーがいつ何を Exchange Online や SharePoint Online で検索したかなどの重要なイベントへのアクセスを提供することで、組織によるフォレンジック調査やコンプライアンス調査の実施をサポートします。 これらの重要なイベントは、起こりうる侵害を調査し、侵害の範囲を決定するのに役立ちます。  高度な監査は、次の重要なイベントを提供します。

- [MailItemsAccessed](#mailitemsaccessed)

- [Send](#send)

- [SearchQueryInitiatedExchange](#searchqueryinitiatedexchange)

- [SearchQueryInitiatedSharePoint](#searchqueryinitiatedsharepoint)

### <a name="mailitemsaccessed"></a>MailItemsAccessed

MailItemsAccessed イベントは、メールボックス監査アクションであり、メール データがメール プロトコルやメール クライアントによってアクセスされたときにトリガーされます。 MailItemsAccessed アクションは、調査者がデータ違反を識別し、侵害された可能性があるメッセージの範囲を特定するのに役立ちます。 攻撃者がメール メッセージにアクセスすると、MailItemsAccessed アクションは、メッセージが実際に読み取られたことを示す明示的な信号がない場合でもトリガーされます (つまり、バインドや同期などのアクセスの種類が監査レコードに記録されます)。

MailItemsAccessed メールボックス アクションは、Exchange Online のメールボックスの監査ログの MessageBind を置き換え、次の改善点を提供します。

- MessageBind は、AuditAdmin ユーザー ログインの種類に対してのみ構成でき、委任または所有者のアクションには適用されません。 MailItemsAccessed は、すべてのログインの種類に適用されます。

- MessageBind は、メール クライアントによるアクセスのみを対象としています。 同期アクティビティには適用されませんでした。 MailItemsAccessed イベントは、バインド アクセスの種類と同期アクセスの種類の両方によってトリガーされます。

- MessageBind アクションによって、同じメール メッセージにアクセスしたときに複数の監査レコードが作成され、「ノイズ」が監査されます。 一方、MailItemsAccessed イベントは、少数の監査レコードに集約されます。

MailItemsAccessed アクティビティの監査レコードの詳細については、「[高度な監査を使用して、侵害されたアカウントを調査する](mailitemsaccessed-forensics-investigations.md)」を参照してください。

MailItemsAccessed 監査レコードを検索するには、Microsoft 365 コンプライアンス センター内の [監査ログ検索ツール](search-the-audit-log-in-security-and-compliance.md)の **Exchange メールボックス アクティビティ** ドロップダウン リストで **メールボックス アイテムへのアクセス** アクティビティを検索できます。

![監査ログ検索ツールで MailItemsAccessed アクションを検索する](../media/AdvAudit_MailItemsAccessed.png)

Exchange Online PowerShell で [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) または [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) コマンドを実行することもできます。

### <a name="send"></a>Send

Send イベントもメールボックス監査アクションであり、ユーザーが次のアクションのいずれかを実行したときにトリガーされます。

- メール メッセージの送信

- メール メッセージへの返信

- メール メッセージの転送

調査担当者は Send イベントを使用して、侵害されたアカウントから送信されたメールを特定することができます。 Send イベントの監査レコードには、メッセージが送信された日時、InternetMessage ID、件名、メッセージに添付ファイルが含まれているかどうかなどのメッセージに関連する情報が含まれています。 この監査情報は、調査担当者が侵害されたアカウントから送信された、または攻撃者によって送信されたメール メッセージに関連する情報を特定するのに役立ちます。 さらに、調査担当者は Microsoft 365 の電子情報開示ツールを使用して (件名やメッセージ ID を使用して) メッセージを検索し、メッセージの送信先である受信者と送信されたメッセージの実際の内容を特定することができます。

Send 監査レコードを検索するには、Microsoft 365 コンプライアンス センター内の [監査ログ検索ツール](search-the-audit-log-in-security-and-compliance.md)の **Exchange メールボックス アクティビティ** ドロップダウン リストで **送信済みメッセージ** アクティビティを検索できます。

![監査ログ検索ツールでの送信済みメッセージ アクションの検索](../media/AdvAudit_SentMessage.png)

Exchange Online PowerShell で [Search-UnifiedAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) または [Search-MailboxAuditLog -Operations Send](https://docs.microsoft.com/powershell/module/exchange/search-mailboxauditlog) コマンドを実行することもできます。

### <a name="searchqueryinitiatedexchange"></a>SearchQueryInitiatedExchange

SearchQueryInitiatedExchange イベントは、ユーザーが Outlook on the web (OWA) の検索バーを使用してメールボックス内のアイテムを検索するときにトリガーされます。 調査担当者は SearchQueryInitiatedExchange イベントを使用し、アカウントを侵害した可能性のある攻撃者がメールボックス内の機密情報を探したり、アクセスしようとしたかどうかを判断することができます。 SearchQueryInitiatedExchange イベントの監査レコードには、検索クエリの実際のテキストなどの情報が含まれています。 攻撃者が実行した可能性のある検索クエリを調査することで、調査担当者は検索されたメール データの意図をより深く理解することができます。

SearchQueryInitiatedExchange 監査レコードを検索するには、コンプライアンス センター内の [監査ログ検索ツール](search-the-audit-log-in-security-and-compliance.md)の **検索アクティビティ** ドロップダウン リストで **実行されたメール検索** アクティビティを検索できます。

![監査ログ検索ツールでの実行されたメール検索アクションの検索](../media/AdvAudit_SearchExchange.png)

また、Exchange Online PowerShell で [Search-UnifiedAuditLog -Operations SearchQueryInitiatedExchange](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) を実行することもできます。

> [!NOTE]
> (特定の E5 ユーザーによって実行された) SearchQueryInitiatedExchange イベントが監査ログの検索結果に含まれるように、Exchange Online PowerShell で次のコマンドを実行する必要があります: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`。<br/><br/>
複数地域環境では、ユーザーのメールボックスが配置されているフォレストで **Set-Mailbox** コマンドを実行する必要があります。 ユーザーのメールボックスの場所を特定するには、次のコマンドを実行します: `Get-Mailbox <user identity> | FL MailboxLocations`。
以前に、ユーザーのメールボックスが配置されているフォレストとは異なるフォレストで `Set-Mailbox -AuditOwner @{Add="SearchQueryInitiated"}` コマンドが実行された場合は、ユーザーのメールボックスから (`Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` を実行して) SearchQueryInitiated 値を削除し、その後でユーザーのメールボックスが配置されているフォレスト内のユーザーのメールボックスに追加する必要があります。

### <a name="searchqueryinitiatedsharepoint"></a>SearchQueryInitiatedSharePoint

メールボックス アイテムの検索と同様に、組織の SharePoint ホーム サイト内のアイテムをユーザーが検索すると、SearchQueryInitiatedSharePoint イベントがトリガーされます。 調査担当者は、SearchQueryInitiatedSharePoint イベントを使用して攻撃者が SharePoint 内の機密情報を見つけようとした (そしてアクセスした可能性がある) かどうかを判断することができます。 SearchQueryInitiatedSharePoint イベントの監査レコードには、検索クエリの実際のテキストも含まれています。 攻撃者が実行した可能性のある検索クエリを調査することで、調査担当者は検索されたファイル データの意図や範囲をより深く理解することができます。

SearchQueryInitiatedSharePoint 監査レコードを検索するには、コンプライアンス センター内の [監査ログ検索ツール](search-the-audit-log-in-security-and-compliance.md)の **検索アクティビティ** ドロップダウン リストで **実行された SharePoint 検索** アクティビティを検索できます。

![監査ログ検索ツールでの実行された SharePoint 検索アクションの検索](../media/AdvAudit_SearchSharePoint.png)

また、Exchange Online PowerShell で [Search-UnifiedAuditLog -Operations SearchQueryInitiatedSharePoint](https://docs.microsoft.com/powershell/module/exchange/search-unifiedauditlog) を実行することもできます。

> [!NOTE]
> (特定の E5 ユーザーによって実行された) SearchQueryInitiatedExchange イベントが監査ログの検索結果に含まれるように、Exchange Online PowerShell で次のコマンドを実行する必要があります: `Set-Mailbox <user identity> -AuditOwner @{Add="SearchQueryInitiated"}`。<br/><br/>
複数地域環境では、ユーザーのメールボックスが配置されているフォレストで **Set-Mailbox** コマンドを実行する必要があります。 ユーザーのメールボックスの場所を特定するには、次のコマンドを実行します: `Get-Mailbox <user identity> | FL MailboxLocations`。
以前に、ユーザーのメールボックスが配置されているフォレストとは異なるフォレストで `Set-Mailbox -AuditOwner @{Add="SearchQueryInitiated"}` コマンドが実行された場合は、ユーザーのメールボックスから (`Set-Mailbox -AuditOwner @{Remove="SearchQueryInitiated"}` を実行して) SearchQueryInitiated 値を削除し、その後でユーザーのメールボックスが配置されているフォレスト内のユーザーのメールボックスに追加する必要があります。

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Office 365 管理アクティビティ API への高帯域幅アクセス

Office 365 管理アクティビティ API を使用して監査ログにアクセスする組織は、発行者レベルの調整制限により制限されていました。 つまり、発行者が複数のお客様に代わってデータをプルする場合、制限はそれらすべてのお客様で共有されていました。

高度な監査のリリースにより、発行者レベルの制限からテナント レベルの制限に移行します。 その結果、各組織は、監査データにアクセスするために独自に完全に割り当てられた帯域幅を取得します。 帯域幅は静的な定義済みの制限ではありませんが、組織内のシート数などの要因の組み合わせでモデル化され、E5 組織は E5 以外よりも多くの帯域幅を利用できます。

すべての組織には、最初に 1 分あたり 2,000 件の要求のベースラインが割り当てられます。 この制限は、組織のシート数とライセンス サブスクリプションに応じて動的に増加します。 E5 組織は、E5 以外の組織の約 2 倍の帯域幅を利用できます。 また、サービスの正常性を保護するために、最大帯域幅の上限も設定されます。

詳細については、「[Office 365 管理アクティビティ API リファレンス](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)」の「API 調整」のセクションを参照してください。

## <a name="set-up-advanced-audit-for-users"></a>ユーザーの高度な監査のセットアップを行う

MailItemsAccessed や Send などの重要なイベントをログに記録する機能などの高度な監査機能を使用するには、ユーザーに適切な E5 ライセンスが割り当てられている必要があります。 さらに、それらのユーザーに対して高度な監査アプリ/サービス プランを有効にする必要があります。 高度な監査アプリがユーザーに割り当てられていることを確認するには、ユーザーごとに次の手順を実行します。

1. [Microsoft 365 管理センター](https://admin.microsoft.com/Adminportal)で、**[ユーザー]** > **[アクティブなユーザー]** の順に移動し、ユーザーを選択します。

2. ユーザー プロパティのポップアップ ページで、**[ライセンスとアプリ]** をクリックします。

3. **[ライセンス]** セクションで、ユーザーに E5 ライセンスが割り当てられていることを確認します。

4. **[アプリ]** セクションを展開して、**[Microsoft 365 高度な監査]** チェック ボックスが選択されていることを確認します。

5. そのチェック ボックスが選択されていない場合は、選択して **[変更の保存]** をクリックします。

   ユーザーの MailItemsAccessed、送信、およびその他の重要なイベントの監査レコードのログ記録は、24  時間以内に開始されます。

グループ ベースのライセンスを使用してユーザーのグループにライセンスを割り当てている組織では、グループに対する Microsoft 365 Advanced Auditing のライセンス割り当てをオフにする必要があります。 変更を保存したら、Microsoft 365 Advanced Auditing がグループに対してオフになっていることを確認します。 その後、グループに対するライセンス割り当てをもう一度オンにします。 グループ ベースのライセンスの手順については、「[Azure Active Directory でのグループ メンバーシップによるユーザーへのライセンスの割り当て](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)」を参照してください。

ユーザー メールボックスまたは共有メールボックスについてログに記録されるメールボックス操作をカスタマイズしている場合、MailItemsAccessed などの新しい既定のメールボックス操作は、これらのメールボックスでは自動的に監査されません。 ログオンの種類ごとに監査されるメールボックス操作の変更については、 「[メールボックスの監査を管理する](enable-mailbox-auditing.md#change-or-restore-mailbox-actions-logged-by-default)」の「既定でログに記録されるメールボックスの操作を変更または復元する」セクションを参照してください。

## <a name="faqs-for-advanced-audit"></a>高度な監査についてよく寄せられる質問

**高度な監査を利用するには、すべてのユーザーに E5 ライセンスが必要ですか ?**

ユーザーレベルの高度な監査機能を利用するには、ユーザーに E5 ライセンスを割り当てる必要があります。 適切なライセンスをチェックして、ユーザーに機能を公開するための機能がいくつかあります。 たとえば、90 日を超えて E5 ライセンスが割り当てられていないユーザーの監査レコードを保持しようとすると、システムはエラー メッセージを返します。

**組織に E5 サブスクリプションがある場合、重要なイベントの監査レコードにアクセスするために何かをする必要はありますか?**

適切なライセンスが割り当てられている対象のお客様とユーザーには、重要な監査イベントにアクセスするためのアクションはありません。

**新しい 10 年間の監査ログ保持アドオン ライセンスはいつ利用できるようになりますか?**

新しい 10 年間の監査ログ保持アドオンは、E5 サブスクリプションをお持ちのお客様を対象に 2021 年初頭より購入できるようになります。

**10 年間の監査ログ保持ポリシーを作成していて、必要なアドオン ライセンスが 2021 年初頭に利用可能となる前に一般提供された場合、組織の監査ログ データはどうなりますか?**

一般提供された後に作成した 10 年間の監査ログ保持ポリシーの対象となる任意の監査ログ データについては、10 年間にわたって保持されます。 2021 年初頭に 10 年間の監査ログ保持アドオン ライセンスが利用可能になったときには、既存の 10 年間の監査データ保持ポリシーによって監査データを保持しているユーザーのためのアドオン ライセンスを購入する必要があります。 また、2021 年初頭にアドオン ライセンスが利用可能になると、10 年間の監査ログ保持ポリシーを新たに作成するときに適切なライセンスが強制されるようになります。

**高度な監査の新しいイベントは、Office 365 管理アクティビティ API で利用できますか ?**

はい。 適切なライセンスを持つユーザーの監査レコードが生成されている限り、Office 365 管理アクティビティ API を介してこれらのレコードにアクセスできます。

**より高い帯域幅は、遅延の改善やより高い SLA を意味しますか ?**

現時点では、高帯域幅は、特に大量の監査シグナルおよび重要な消費パターンを持つ組織に対して、より良いパイプラインを提供します。 より高い帯域幅により、遅延が改善される可能性があります。 ただし、高帯域幅に関連する SLA はありません。 標準的な遅延はドキュメント化されており、これらの遅延は高度な監査のリリースでは変更されません。
