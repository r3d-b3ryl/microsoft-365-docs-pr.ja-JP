---
title: スパム対策メッセージ ヘッダー
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: 2e3fcfc5-5604-4b88-ac0a-c5c45c03f1db
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online Protection (EOP) によってメッセージに追加されるヘッダー フィールドについて学習することができます。 これらのヘッダー フィールドは、メッセージとそのメッセージがどのように処理されたかについての情報を提供します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8ce0b906bb627a7de11e5a8a6db02c9c6f330a62
ms.sourcegitcommit: 2acd9ec5e9d150389975e854c7883efc186a9432
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755358"
---
# <a name="anti-spam-message-headers-in-microsoft-365"></a>Microsoft 365 のスパム対策メッセージ ヘッダー

In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, EOP scans and inserts the **X-Forefront-Antispam-Report** header into each inbound email message. The fields in this header can help provide administrators with information about the message and about how it was processed. The fields in the **X-Microsoft-Antispam** header provide additional information about bulk mail and phishing. In addition to these two headers, Exchange Online Protection also inserts email authentication results for each message it processes in the **Authentication-results** header.

さまざまなメール クライアントでメール メッセージ ヘッダーを表示する方法については、「[Outlook のインターネット メッセージ ヘッダーの表示](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)」を参照してください。

> [!TIP]
> メッセージ ヘッダーの内容は、コピーして[メッセージ ヘッダー アナライザー](https://mha.azurewebsites.net/) ツールに貼り付けることができます。 このツールは、ヘッダーを解析し、より読みやすい形式にします。

## <a name="x-forefront-antispam-report-message-header-fields"></a>X-Forefront-Antispam-Report メッセージ ヘッダー フィールド

メッセージ ーヘッダーの情報を取得したら、**X-Forefront-Antispam-Report** ヘッダーを見つけます。 このヘッダーには、セミコロン (;) で区切られた複数のヘッダー フィールドと値のペアがあります。 例:

`...CTRY:;LANG:hr;SCL:1;SRV:;IPV:NLI;SFV:NSPM;PTR:;CAT:NONE;SFTY:;...`

次の表に個々のフィールドと値の説明を示します。

> [!NOTE]
> **X-Forefront-Antispam-Report** ヘッダーには、多くのさまざまなヘッダー フィールドと値が含まれています。 テーブルに記載されていないこのヘッダー内のその他のフィールドは、Microsoft スパム対策チームが診断のために専用で使用します。

|||
|---|---|
|**ヘッダー フィールド**|**説明**|
|ARC|ARC プロトコルには次のヘッダーがあります。 <ul><li>AAR: DMARC からの認証結果ヘッダーのコンテンツを記録します。</li><li>AMS: このヘッダーには、メッセージの暗号化署名が含まれます。</li><li>AS: メッセージ ヘッダーの暗号化署名が含まれます。 このヘッダーには、"cv=" と呼ばれるチェーン検証のタグが含まれており、チェーン検証の結果が **none**、**pass**、または **fail** として含まれています。</li></ul>|
|CAT:|メッセージに適用される保護ポリシーです。 <ul><li>BULK: バルク</li><li>DIMP: ドメイン偽装</li><li>GIMP: メールボックス インテリジェンスに基づく偽装</li><li>HPHSH または HPHISH: 高精度フィッシング</li><li>HSPM: 高確度スパム</li><li>MALW: マルウェア</li><li>PHSH: フィッシング</li><li>SPM: スパム</li><li>SPOOF: なりすまし</li><li>UIMP: ユーザー偽装</li><li>AMP: マルウェア対策</li><li>SAP: 添付ファイル保護</li><li>OSPM: 送信スパム</li></ul><br/>受信メッセージには、複数の種類の保護と複数の検出スキャンによりフラグが付けられる場合があります。 ポリシーの優先度はそれぞれ異なり、優先度が最も高いポリシーが最初に適用されます。 詳細については、「[複数の保護方法および検出スキャンがメールで実行される場合に適用されるポリシー](how-policies-and-protections-are-combined.md)」を参照してください。|
|CIP: \[IP アドレス\]|接続 IP アドレス。 この IP アドレスは、IP 許可一覧または IP 禁止一覧で使用できます。 詳細については、「[接続フィルターを構成する](configure-the-connection-filter-policy.md)」を参照してください。|
|CTRY|接続 IP アドレスから特定される発信国ですが、発信元の送信 IP アドレスとは異なる可能性があります。|
|H:\[helostring\]|接続メール サーバーの HELO または EHLO 文字列。|
|IPV:CAL|送信元 IP アドレスが IP 許可一覧にあるため、メッセージのスパム フィルタリングが省略されました。 詳細については、「[接続フィルターを構成する](configure-the-connection-filter-policy.md)」を参照してください。|
|IPV:NLI|IP アドレスが IP 評価リストに掲載されていませんでした。|
|LANG|メッセージが作成された言語であり、国番号 (たとえば、ロシア語は ru_RU) で指定されます。|
|PTR:\[ReverseDNS\]|逆引き DNS 参照とも呼ばれる、送信元の IP アドレスの PTR レコード。|
|SCL|メッセージの SCL (Spam Confidence Level) です。 値が高いほど、メッセージがスパムである可能性が高くなります。 詳細については、「[Spam Confidence Level (SCL)](spam-confidence-levels.md)」を参照してください。|
|SFTY|メッセージはフィッシングとして識別され、次のいずれかの値が付けられます。 <ul><li>9.1: 既定値。 メッセージにフィッシングの URL が含まれているか、他のフィッシング コンテンツが含まれている可能性があります。あるいは、Microsoft 365 への送信前に別のメール フィルター (オンプレミスの Exchange など) によってフィッシングとしてマークされていた可能性があります。</li><li>9.11: [組織内または自己完結型のスプーフィング](anti-spoofing-protection.md#different-types-of-spoofing)。 差出人ヘッダー内の送信者のメール ドメインが、受信ドメインと同じ組織であるか、または同じ組織の一部であるため、メッセージがスプーフィング対策チェックにパスしませんでした。 組織内スプーフィングの安全性に関するヒントがメッセージに追加されます。</li><li>9.19: ドメインの偽装。 送信側ドメインが、ATP フィッシング詐欺対策ポリシーで指定されている保護ドメイン (受信者の組織が所有するドメインまたはカスタム ドメイン) を偽装している可能性があります。 ドメインの偽装の安全性に関するヒントがメッセージに追加されます (安全性に関するヒントが ATP フィッシング詐欺対策ポリシーで有効になっている場合)。</li><li>9.20: ユーザーの偽装。 送信ユーザーが、受信者の組織内のユーザー、または ATP フィッシング詐欺対策ポリシーで指定されている保護ユーザーを偽装しようとしています。 ユーザーの偽装の安全性に関するヒントがメッセージに追加されます (安全性に関するヒントが ATP フィッシング詐欺対策ポリシーで有効になっている場合)。</li><li>9.21: [クロスドメイン スプーフィング](anti-spoofing-protection.md#different-types-of-spoofing)。 差出人ヘッダー内の送信者のメール ドメインが外部ドメインであり、認証されないため、メッセージがスプーフィング対策チェックにパスしませんでした。 [CompAuth](#authentication-results-message-header-fields-used-by-microsoft-email-authentication) と組み合わせて使用されます。</li><li>9.22: ユーザーが、オーバーライドされた差出人セーフ リストを持っている点を除き、9.21 と同じです。 </li><li>9.23: ただし、組織が、オーバーライドされた許可された送信者またはドメインを持っている点を除き、9.22 と同じです。</li><li>9.24: ユーザーが、オーバーライドされた Exchange メール フロー ルール (トランスポート ルールとも呼ばれます) を持っている点を除き、9.23 と同じです。</li></ul>|
|SFV:BLK|メッセージがユーザーの Outlook 受信拒否アドレス (ユーザーの受信拒否リスト) から送信されているため、フィルター処理が省略され、メッセージはブロックされました。<br/></br> 管理者がユーザーの受信拒否リストを管理する方法の詳細については、「[Exchange Online メールボックスで迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。|
|SFV:NSPM|スパム フィルタリングによって、メッセージがスパムではないとしてマークされ、意図された受信者に送信されました。|
|SFV:SFE|メッセージがユーザーの Outlook 上の信頼できる差出人のアドレス (ユーザーの信頼できる差出人のリスト) から送信されているため、フィルター処理が省略され、メッセージはそのまま配信されました。<br/></br> 管理者がユーザーの信頼できる差出人のリストを管理する方法の詳細については、「[Exchange Online メールボックスで迷惑メール設定を構成する](configure-junk-email-settings-on-exo-mailboxes.md)」を参照してください。|
|SFV:SKA|メッセージがスパム対策ポリシーの許可された送信者リストまたは許可されたドメイン リストのエントリと一致したため、メッセージはスパム フィルタリングが省略され、受信トレイに配信されました。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。|
|SFV:SKB|メッセージは、スパム対策ポリシーの受信拒否リストまたはブロックされているドメイン リストのエントリと一致したため、スパムとしてマークされました。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。|
|SFV:SKI|SFV:SKN と同様に、メッセージは別の理由 (例: テナント内の組織内メールなど) でスパム フィルタリングが省略されました。|
|SFV:SKN|メッセージは、スパム フィルタリングによって処理される前にスパムではないとしてマークされました (例: メッセージは、メール フロー ルールによって SCL -1 または**スパム フィルタリングのバイパス**としてマークされました)。|
|SFV:SKQ|メッセージは検疫から解放され、目的の受信者に送信されました。|
|SFV:SKS|メッセージは、スパム フィルタリングによって処理される前にスパムとしてマークされました (例: メッセージは、メール フロー ルールによって SCL 5 から 9 としてマークされました)。|
|SFV:SPM|スパム フィルタリングによって、メッセージがスパムとしてマークされました。|
|SRV:BULK|メッセージは、スパムフィルタリングおよび Bulk Complaint Level (BCL) のしきい値により、バルク メールとして識別されました。 _MarkAsSpamBulkMail_ パラメーターが `On` の場合 (既定はオン)、バルク メール メッセージは高確度迷惑メール (SCL 9) としてマークされます。 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。|
|X-CustomSpam: \[ASFOption\]|メッセージは高度なスパム フィルター (ASF) の設定と一致しました。 各 ASF 設定の X ヘッダーの値を確認するには、「[高度なスパム フィルター (ASF) の設定](advanced-spam-filtering-asf-options.md)」を参照してください。|
|

## <a name="x-microsoft-antispam-message-header-fields"></a>X-Microsoft-Antispam メッセージ ヘッダー フィールド

The following table describes useful fields in the **X-Microsoft-Antispam** message header. Other fields in this header are used exclusively by the Microsoft anti-spam team for diagnostic purposes.

|||
|---|---|
|**ヘッダー フィールド**|**説明**|
|BCL|メッセージの Bulk Complaint Level (BCL)。 BCL が高いほど、バルク メール メッセージ (_グレー メール_とも呼ばれます) が好ましくない内容である可能性が高い (したがって、スパムである可能性が高い) ことを示します。 詳細については、「[Bulk Complaint Level (BCL)](bulk-complaint-level-values.md)」を参照してください。|
|

## <a name="authentication-results-message-header"></a>Authentication-results メッセージ ヘッダー

メール サーバーが電子メール メッセージを受信すると、SPF、DKIM、および DMARC に対するチェックの結果が Microsoft 365 によって、**Authentication-Results** メッセージ ヘッダーに記録またはスタンプされます。

### <a name="check-stamp-syntax-and-examples"></a>スタンプの構文と例を確認する

The following syntax examples show a portion of the text "stamp" that Microsoft 365 applies to the message header for each email that undergoes an email authentication check when it is received by our mail servers. The stamp is added to the **Authentication-Results** header.

#### <a name="syntax-spf-check-stamp"></a>構文:SPF check stamp

SPF の場合は、次の構文を適用します。

```text
spf=<pass (IP address)|fail (IP address)|softfail (reason)|neutral|none|temperror|permerror> smtp.mailfrom=<domain>
```

##### <a name="examples-spf-check-stamp"></a>例:SPF check stamp

```text
spf=pass (sender IP is 192.168.0.1) smtp.mailfrom=contoso.com
spf=fail (sender IP is 127.0.0.1) smtp.mailfrom=contoso.com
```

#### <a name="syntax-dkim-check-stamp"></a>構文:DKIM check stamp

DKIM の場合は、次の構文を適用します。

```text
dkim=<pass|fail (reason)|none> header.d=<domain>
```

##### <a name="examples-dkim-check-stamp"></a>例:DKIM check stamp

```text
dkim=pass (signature was verified) header.d=contoso.com
dkim=fail (body hash did not verify) header.d=contoso.com
```

#### <a name="syntax-dmarc-check-stamp"></a>構文:DMARC check stamp

DMARC の場合は、次の構文を適用します。

```text
dmarc=<pass|fail|bestguesspass|none> action=<permerror|temperror|oreject|pct.quarantine|pct.reject> header.from=<domain>
```

##### <a name="examples-dmarc-check-stamp"></a>例:DMARC check stamp

```text
dmarc=pass action=none header.from=contoso.com
dmarc=bestguesspass action=none header.from=contoso.com
dmarc=fail action=none header.from=contoso.com
dmarc=fail action=oreject header.from=contoso.com
```

### <a name="authentication-results-message-header-fields-used-by-microsoft-email-authentication"></a>Microsoft の電子メールの認証で使用される Authentication-Results メッセージ ヘッダー フィールド

フィールドと各電子メールの認証チェックに使用できる値を次の表に示します。

|||
|---|---|
|**ヘッダー フィールド**|**説明**|
|action|Indicates the action taken by the spam filter based on the results of the DMARC check. For example: <ul><li>**oreject** または **o.reject**: 拒否の上書き (override reject) の略語。 この場合、Microsoft 365 は、ポリシーが p=reject に設定されている DMARC TXT レコードが属するドメインから DMARC チェックに失敗したメッセージを受信すると、このアクションを使用します。 Microsoft 365 はメッセージを削除または拒否する代わりに、スパムとしてメッセージにマークを付けます。 このように Microsoft 365 が構成されている理由の詳細については、「[Microsoft 365 が DMARC に失敗した受信メールを処理する方法](use-dmarc-to-validate-email.md#how-microsoft-365-handles-inbound-email-that-fails-dmarc)」を参照してください。</li><li>**pct.quarantine**: DMARC をパスしないメッセージのうち、100% 未満のある割合のメッセージはいずれにせよ配信されることを示します。 これは、メッセージが DMARC に失敗してポリシーが検疫に設定されますが、pct フィールドは 100% に設定されず、システムは指定されたドメインのポリシーに従って、DMARC アクションを適用しないことをランダムに判断しているということです。</li><li>**pct.reject**: DMARC をパスしないメッセージのうち、100% 未満のある割合のメッセージはいずれにせよ配信されることを示します。 これは、メッセージが DMARC に失敗してポリシーが拒否に設定されますが、pct フィールドは 100% に設定されず、システムは指定されたドメインのポリシーに従って、DMARC アクションを適用しないことをランダムに判断しているということです。</li><li>**permerror**: DMARC の評価時に永続的なエラーが発生したことを示します (DNS で正しくない形式の DMARC TXT レコードが見つかった場合など)。 このメッセージを再送信しようとしても、結果が異なる可能性はほとんどありません。 その代わりに、ドメインの所有者に問い合わせて問題を解決する必要があります。</li><li>**temperror**: DMARC の評価時に一時的なエラーが発生したことを示します。 メールが正しく処理されるように、少し時間をおいてからメッセージを送信するように、送信者に要求することもできます。</li></ul>|
|compauth|複合認証の結果。 Microsoft 365 が、SPF、DKIM、DMARC などのさまざまな種類の認証を組み合わせて、メッセージが認証されているかどうかを判断するために使用されます。 評価の基準として、差出人: ドメインを使用します。|
|dkim|Describes the results of the DKIM check for the message. Possible values include: <ul><li>**pass**: メッセージの DKIM チェックにパスしたことを示します。</li><li>**fail (理由)**: メッセージの DKIM チェックに失敗したことと、その理由を示します。 たとえば、メッセージが署名されていない場合、署名を認証できない場合などです。</li><li>**none**: メッセージが署名されていないことを示します。 これは、ドメインに DKIM レコードがあるかどうかや、DKIM レコードが結果を評価しない (このメッセージが署名されていない点のみ) ことを示しますが、これらを示さない場合もあります。</li></ul>|
|dmarc|Describes the results of the DMARC check for the message. Possible values include: <ul><li>**pass**: メッセージの DMARC チェックにパスしたことを示します。</li><li>**fail**: メッセージの DMARC チェックに失敗したことを示します。</li><li>**bestguesspass**: ドメインの DMARC TXT レコードが存在しないことを示します。ただし、レコードが存在していた場合、メッセージの DMARC チェックはパスしていたことになります。 これは、`5321.MailFrom` アドレスのドメイン (MAIL FROM アドレス、P1 送信者、またはエンベロープの差出人とも呼ばれます) が `5322.From` アドレスのドメイン (From アドレスまたは P2 送信者とも呼ばれます) と一致するためです。</li><li>**none**: DNS に送信側ドメインの DMARC TXT レコードが存在していないことを示します。|
|header.d|Domain identified in the DKIM signature if any. This is the domain that's queried for the public key.|
|header.from|メール メッセージ ヘッダーの `5322.From` アドレスのドメイン (From アドレスまたは P2 送信者とも呼ばれます)。 受信者には、メール クライアントの From アドレスが表示されます。|
|理由|複合認証にパスした、または失敗した理由。 値は 3 桁のコードです。 以下に例を示します。 <ul><li>**000**: メッセージが明示的な認証をパスしなかったことを意味します (`compauth=fail`)。 たとえば、メッセージが DMARC fail を受け取り、検疫または却下のアクションが適用された場合などです。</li><li>**001** は、メッセージが暗黙的な認証をパスしなかったことを示します (`compauth=fail`)。 これは、送信側ドメインがメール認証レコードを公開していないか、公開していた場合でも弱い失敗ポリシー (SPF soft fail または neutral、`p=none` の DMARC ポリシー) があったことを意味します。</li><li>**002**: 組織に、スプーフィングされたメールの送信を明示的に禁止する送信者/ドメインのペアのポリシーがあることを意味します。 この設定は、管理者が手動で設定します。</li><li>**010**: メッセージが拒否または検疫のアクションによって DMARC をパスせず、送信側ドメインが組織の承認済みドメインに含まれていることを意味します (これは、自己完結型 (つまり組織内の) スプーフィングの一部です)。</li><li>**1xx** または **7xx**: メッセージが認証をパスしたことを意味します (`compauth=pass`)。 最後の 2 桁の数字は Microsoft 365 で使用される内部コードです。</li><li>**2xx**: メッセージが暗黙的な認証を soft-pass したことを意味します (`compauth=softpass`)。 最後の 2 桁の数字は Microsoft 365 で使用される内部コードです。</li><li>**3xx**: メッセージに対して複合認証のチェックが実行されなかったことを意味します (`compauth=none`)。</li><li>**4xx** または **9xx**: メッセージに対する複合認証が省略されたことを意味します (`compauth=none`)。 最後の 2 桁の数字は Microsoft 365 で使用される内部コードです。</li><li>**6xx**: メッセージは暗黙的なメール認証をパスしなかったが、送信側ドメインが組織の承認済みドメインのいずれかであることを意味します (これは、自己完結型 (つまり組織内の) スプーフィングの一部です)。</li></ul>|
|smtp.mailfrom|`5321.MailFrom` アドレスのドメイン (MAIL FROM アドレス、P1 送信者、またはエンベロープの差出人とも呼ばれます)。 これは、配信不能レポート (NDR またはバウンス メッセージとも呼ばれます) に使用されるメール アドレスです。|
|spf|Describes the results of the SPF check for the message. Possible values include: <ul><li>**pass (IP アドレス)**: メッセージの SPF チェックにパスしたことを示します。送信者の IP アドレスが含まれます。 送信者のドメインに代わってメールを送信または中継する許可がクライアントに与えられています。</li><li>**fail (IP アドレス)**: メッセージの SPF チェックに失敗したことを示します。送信者の IP アドレスが含まれます。 _hard fail_ と呼ばれることもあります。</li><li>**softfail (理由)**: SPF レコードにより、ホストには送信する許可がないと指定されたことを示しますが、SPF レコードが展開中であることも示します。</li><li>**neutral**: IP アドレスが許可されているかどうかをアサートしていないことを、SPF レコードが明示的に宣言したことを示します。</li><li>**none**: ドメインに SPF レコードがないか、SPF レコードが結果に対して評価されないことを示します。</li><li>**temperror**: DNS エラーなど、一時的なエラーが発生した可能性があることを示します。 時間をおいて再試行すれば、管理者がアクションを実行しなくても、成功する場合があります。</li><li>**permerror**: 永続的なエラーが発生したことを示します。 これは、ドメインに不正な形式の SPF レコードがある場合に発生します。</li></ul>|
|
