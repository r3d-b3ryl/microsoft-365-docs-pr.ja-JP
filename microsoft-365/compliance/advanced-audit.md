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
description: Microsoft 365 の高度な監査では、組織におけるフォレンシックおよびコンプライアンスの調査に役立つ新しい監査機能を提供します。
ms.openlocfilehash: bdde2552d2c5ccd790740e1f9077e5d26391e920
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634545"
---
# <a name="advanced-audit-in-microsoft-365"></a>Microsoft 365 の高度な監査

Microsoft 365 の[統合監査機能](search-the-audit-log-in-security-and-compliance.md)を使用すると、組織は Microsoft 365 のさまざまなサービスにわたって、さまざまな種類の監査済みアクティビティを可視化できます。 Microsoft 365 の高度な監査のリリースにより、組織におけるフォレンシックおよびコンプライアンスの調査に役立つ新しい監査機能が追加されました。

> [!NOTE]
> 高度な監査は、Office 365 E5 または Microsoft 365 Enterprise E5 サブスクリプションを持つ組織で利用できます。 さらに、Microsoft 365 E5 コンプライアンス アドオン ライセンスは、監査ログの長期保持や調査のための重要なイベントへのアクセスと同様に、高度な監査機能にユーザーごとのライセンスが必要な場合に、ユーザーに割り当てることができます。

この記事では、これらの高度な監査機能の概要について説明します。

## <a name="long-term-retention-of-audit-logs"></a>監査ログの長期保持

高度な監査では、Exchange、SharePoint、および Azure Active Directory の監査レコードが 1 年間保持されます。 これは、アクティビティが発生したサービスを示す**ワークロード** プロパティの**Exchange**、**SharePoint**、または **AzureActiveDirectory** の値を含む任意の監査レコードを 1 年間保持する既定の監査ログの保持ポリシーによって実現されます。 これは、フォレンシックまたはコンプライアンスに関する継続的な調査に役立ちます。 詳細については、「監査ログの保持ポリシーの管理」の「[既定の監査ログの保持ポリシー](audit-log-retention-policies.md#default-audit-log-retention-policy)」セクションを参照してください。

## <a name="audit-log-retention-policies"></a>監査ログの保持ポリシー

(前のセクションで説明した) 既定の監査ログの保持ポリシーが適用されていない他のサービスで生成されたすべての監査レコードは、90 日間保持されます。 ただし、カスタマイズした監査ログの保持ポリシーを作成して、最大 1 年間他の監査レコードを保持できます。 次の 1 つ以上の基準に基づいて、監査レコードを保持するポリシーを作成できます。

- 監査されたアクティビティが発生する Microsoft 365 サービス

- 特定の監査済みアクティビティ

- 監査済みアクティビティを実行するユーザー

特定のポリシーが他のポリシーよりも優先されるように、ポリシーおよび優先度のレベルに一致する監査レコードを保持する期間を指定することもできます。 また、組織の一部またはすべてのユーザーに対して Exchange、SharePoint、または Azure Active Directory 監査レコードを 1 年未満で保持する必要がある場合は、カスタム監査ログの保持ポリシーが既定の監査保持ポリシーよりも優先されます。 詳細については、「[監査ログ保持ポリシーを管理する](audit-log-retention-policies.md)」を参照してください。

## <a name="access-to-crucial-events-for-investigations"></a>調査のための重要なイベントへのアクセス

重要なセキュリティ - セキュリティ関連の重要な監査イベントおよびコンプライアンス関連の監査イベントは、違反の可能性やその他のフォレンジック調査の調査に役立つイベントです。 リリースする最初の重要なイベントは、*MailItemsAccessed* メールボックスの監査アクションです。 このアクションは、メール プロトコルとメール クライアントがメール データにアクセスしたときにトリガーされます。 MailItemsAccessed アクションは、調査者がデータ違反を識別し、侵害された可能性があるメッセージの範囲を特定するのに役立ちます。 攻撃者がメール メッセージにアクセスすると、MailItemsAccessed アクションは、メッセージが実際に読み取られたことを示す明示的な信号がない場合でもトリガーされます (つまり、バインドや同期などのアクセスの種類が監査レコードに記録されます)。

新しい MailItemsAccessed メールボックス アクションは、Exchange Online のメールボックスの監査ログインの MessageBind を置き換え、次の改良点を提供します。

- MessageBind は、AuditAdmin ユーザー ログインの種類に対してのみ構成でき、委任または所有者のアクションには適用されません。 MailItemsAccessed は、すべてのログインの種類に適用されます。

- MessageBind は、メール クライアントによるアクセスのみを対象としています。 同期アクティビティには適用されませんでした。 MailItemsAccessed イベントは、バインド アクセスの種類と同期アクセスの種類の両方によってトリガーされます。

- MessageBind アクションによって、同じメール メッセージにアクセスしたときに複数の監査レコードが作成され、「ノイズ」が監査されます。 一方、MailItemsAccessed イベントは、少数の監査レコードに集約されます。

MailItemsAccessed アクティビティの監査レコードの詳細については、「[高度な監査を使用して、侵害されたアカウントを調査する](mailitemsaccessed-forensics-investigations.md)」を参照してください。

### <a name="search-for-mailitemsaccessed-audit-records"></a>MailItemsAccessed 監査レコードを検索する

MailItemsAccessed 監査レコードを検索するには、Office 365 セキュリティ/コンプライアンス センター内の [監査ログ検索ツール](search-the-audit-log-in-security-and-compliance.md) の **Exchange メールボックス アクティビティ** ドロップダウン リストで **メールボックス アイテムへのアクセス** アクティビティを検索できます。

![監査ログ検索ツールで MailItemsAccessed アクションを検索する](../media/MailItemsAccessedSCC1.png)

Exchange Online PowerShell で [Search-UnifiedAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-unifiedauditlog) または [Search-MailboxAuditLog -Operations MailItemsAccessed](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-audit/search-mailboxauditlog) コマンドを実行することもできます。

## <a name="high-bandwidth-access-to-the-office-365-management-activity-api"></a>Office 365 管理アクティビティ API への高帯域幅アクセス

Office 365 管理アクティビティ API を使用して監査ログにアクセスする組織は、発行者レベルの調整制限により制限されていました。 つまり、発行者が複数のお客様に代わってデータをプルする場合、制限はそれらすべてのお客様で共有されていました。

高度な監査のリリースにより、発行者レベルの制限からテナント レベルの制限に移行します。 その結果、各組織は、監査データにアクセスするために独自に完全に割り当てられた帯域幅を取得します。 帯域幅は静的な定義済みの制限ではありませんが、組織内のシート数などの要因の組み合わせでモデル化され、E5 組織は E5 以外よりも多くの帯域幅を利用できます。

すべての組織には、最初に 1 分あたり 2,000 件の要求のベースラインが割り当てられます。 この制限は、組織のシート数とライセンス サブスクリプションに応じて動的に増加します。 E5 組織は、E5 以外の組織の約 2 倍の帯域幅を利用できます。 また、サービスの正常性を保護するために、最大帯域幅の上限も設定されます。

詳細については、「[Office 365 管理アクティビティ API リファレンス](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference#api-throttling)」の「API 調整」のセクションを参照してください。

## <a name="faqs-for-advanced-audit"></a>高度な監査についてよく寄せられる質問

**高度な監査にはどこからアクセスできますか ?**

高度な監査が組織に展開された後、監査ログ保持ポリシーを作成し、[Office 365 セキュリティ/コンプライアンス センター](https://protection.office.com) の監査ログ検索ツールを使用して MailItemsAccessed 監査レコードを検索できます。 今後数週間以内に、[Microsoft 365 コンプライアンス センター](https://compliance.microsoft.com) に高度な監査を展開するよう取り組んでいます。

**高度な監査を利用するには、すべてのユーザーに E5 ライセンスが必要ですか ?**

ユーザーレベルの高度な監査機能を利用するには、ユーザーに E5 ライセンスを割り当てる必要があります。 適切なライセンスをチェックして、ユーザーに機能を公開するための機能がいくつかあります。 たとえば、90 日を超えて E5 ライセンスが割り当てられていないユーザーの監査レコードを保持しようとすると、システムはエラー メッセージを返します。

**E5 サブスクリプションがあり、E5 ライセンスが割り当てられているユーザーがいるにもかかわらず、組織に高度な監査が表示されないのはなぜですか ?**

適切なライセンスが設定されていても、組織で高度な監査機能 (監査ログ保持ポリシーの作成機能や MailItemsAccessed 監査レコードのログなど) が利用できない可能性があります。 これが発生しているのは、高度な監査パッケージが組織にまだ展開されていないためです。 これは一時的なライセンス バックフィルの問題であり、影響を受けている組織では今後数週間で解決されるはずです。 この問題を軽減するには、E5 ユーザーごとに次の手順を実行してください。

1. Microsoft 365 管理センターで、**[ユーザー]、[アクティブなユーザー]** の順に移動し、ユーザーを選択します。

2. ユーザー プロパティのポップアップ ページで、[**ライセンスとアプリ**] をクリックします。

3. **アプリ** セクションを展開し、次のいずれかの操作を行います。

   a. [**Microsoft 365 Advanced Auditing**] チェックボックスが選択されていない場合、選択して [**変更の保存**] をクリックします。 このユーザーの MailItemsAccessed アクションの監査レコードは、24 時間以内に検索可能になります。

   b. [**Microsoft 365 Advanced Auditing**] チェックボックスが選択されている場合、選択を外して [**変更の保存**] をクリックします。 手順 4 を参照してください。

4. 手順 3 でチェックボックスを外した場合は、60 分待ってから手順 3a を繰り返し、Microsoft 365 Advanced Auditing アプリを有効にします。

**組織が監査レコード 1 年間保持のプライベート プレビュー中であった場合はどうなりますか ?**

プレビュー プログラムからの監査保持ポリシーは、カスタム監査保持ポリシーで上書きおよび変更しない限り保持されます。

**組織が監査ログを 1 年以上保持したい場合はどうなりますか ?**

監査記録の保存期間を延長する方法および可能性についてのオプションを検討しています。 [Office 365 User Voice](https://office365.uservoice.com/forums/289138-office-365-security-compliance?category_id=137187) で監査記録の長期保存についてのフィードバックを提供することができます。

**組織に E5 サブスクリプションがある場合、MailItemsAccessed イベントの監査レコードにアクセスするために何かをする必要はありますか ?**

資格のあるお客様には、MailItemsAccessed イベントにアクセスするためのアクションはありません。 ただし、このトピックで説明したように、ライセンス バックフィルの問題によって発生する遅延により、MailItemsAccessed イベントの監査レコードが監査ログ検索で返されない場合があります。 この場合、MailItemsAccessed 監査レコードの検索セクションの指示に従ってください。

**今年、追加のイベントをリリースする予定はありますか ?**

はい。今後数か月以内に、調査に不可欠な新しいイベントをリリースする予定です。 リリース日が近づいたら、これらの新しいイベントに関する情報を [Microsoft 365 ロードマップ](https://www.microsoft.com/microsoft-365/roadmap) に投稿します。

**高度な監査の新しいイベントは、Office 365 管理アクティビティ API で利用できますか ?**

はい。 適切なライセンスを持つユーザーの監査レコードが生成されている限り、Office 365 管理アクティビティ API を介してこれらのレコードにアクセスできます。

**より高い帯域幅は、遅延の改善やより高い SLA を意味しますか ?**

現時点では、高帯域幅は、特に大量の監査シグナルおよび重要な消費パターンを持つ組織に対して、より良いパイプラインを提供します。 これにより、遅延が改善される可能性があります。 ただし、高帯域幅に関連する SLA はありません。 標準的な遅延はドキュメント化されており、これらは高度な監査のリリースでは変更されません。
