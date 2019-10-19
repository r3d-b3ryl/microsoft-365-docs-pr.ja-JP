---
title: EOP および Office 365 の構成のベストプラクティス-ATP のセキュリティ、ベストプラクティス、設定、推奨事項、送信者ポリシーのフレームワーク、ドメインベースのメッセージの報告と適合性、DomainKeys で識別されたメール、手順、動作のしくみ
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/18/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6f64f2de-d626-48ed-8084-03cc72301aa4
ms.collection:
- M365-security-compliance
description: Exchange Online Protection (EOP) と Advanced Threat Protection (ATP) のセキュリティ設定のベストプラクティスについて 推奨事項 積極的に使用する必要があるもの Advanced Threat Protection (ATP) も使用している場合、どのようなエクストラを利用できますか?
ms.openlocfilehash: b40b4189ed996e1b2f671b77602630f2a98966a5
ms.sourcegitcommit: ffdf576fbc62c4c316f6d8061d2bd973e7df9f56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/19/2019
ms.locfileid: "37598301"
---
# <a name="best-practices-for-configuring-eop-and-office-365-atp-security"></a>EOP および Office 365 の ATP セキュリティを構成するためのベストプラクティス

Exchange Online Protection (EOP) は、E3 Office 365 サブスクリプションのセキュリティの中核となります。 E3 お客様は、Office 365 Advanced Threat Protection (ATP) のサブスクリプションを購入することもできます。 「E5 Office 365 サブスクリプション」で利用可能な追加のセキュリティを活用するために、ATP プラン1または ATP Plan 2。

EOP で推奨およびアグレッシブと呼ばれる2つのセキュリティレベルについて説明し、両方のレベルのセキュリティで機能を使用する方法についてのコメントを示します。 セクションはメールの検証と認証で始まります。これには、Office 365 の外部にある一部の tinkering、DNS、および送信メールのセキュリティを確保するため、メールのリソースに対して優れた市民をテナント化します。 これらの設定はサブスクリプションを保護するのに最適です。


## <a name="email-authentication"></a>電子メール認証

SPF、DKIM、DMARC は、Sender Policy Framework、DomainKeys で識別されたメール、ドメインベースのメッセージ認証、レポート、および適合性 (非常に高い) の略語で、電子メールの認証と検証の基盤となります。

これらのメソッドは、Office 365 からの送信電子メールを処理し、ドメインからの電子メールが有効であることを宛先システムが信頼することをサポートします。 これは、Office 365 の*外部*に構成することについて説明する唯一のベストプラクティスであり、DNS に含まれています。 特定の構成手順については、「セキュリティとコンプライアンスの目次」の「[電子メールの検証と認証](https://docs.microsoft.com/office365/securitycompliance/how-office-365-uses-spf-to-prevent-spoofing)」セクションを参照してください。


|セキュリティ機能の名前  |推奨 |性  |Comment  |
|---------|---------|---------|---------|
|[SPF レコードを作成する](https://docs.microsoft.com/office365/securitycompliance/set-up-spf-in-office-365-to-help-prevent-spoofing)    | はい        |    はい     |   -      |
|[ドメインの DKIM 署名を構成する](https://docs.microsoft.com/office365/securitycompliance/use-dkim-to-validate-outbound-email)     |  はい       |    はい     |  -       |
|[Reject または quarantine アクションを使用して DMARC を実装する](https://docs.microsoft.com/office365/securitycompliance/use-dmarc-to-validate-email)     |   はい      |     はい    |   推奨される場合は action = none、アグレッシブの場合は action = reject を使用します。     |

> [!IMPORTANT]
> セキュリティロールとアクセス許可を操作するには、Office 365 またはセキュリティ/コンプライアンスセンターに適切な役割を持っていることを確認してください。 Azure Active Directory の*セキュリティ管理者*、Office 365 の*全体管理者*、または Exchange Online/Exchange Online Powershell の*exchange online 組織マネージャー*の場合は、準備が整っています。

## <a name="anti-spam-anti-malware-and-anti-phishing"></a>スパム対策、マルウェア対策、およびフィッシング対策

スパム対策とマルウェア対策の両方が EOP の機能です。 スパムフィルター処理 (既定では Office 365) は、すべてのメールをスキャンし、各メールにスパム信頼レベル (SCL) 値を割り当てます。 わかりやすくするために、この目的はメールがスパムであるかどうかを列挙することです。 -1 などの低値は、信頼できる差出人からのスパムではないため、ユーザーの受信トレイにあります。 7、8、9などの高スコアは、非常に疑わしい、またはユーザーの迷惑メールに対する既知のスパム送信者とヘッド、または管理者がアクセス可能な検疫のいずれかです。

また、マルウェアフィルター処理は、Office 365 では既定でオンになっています。 スパム対策フィルターと同様に、マルウェア対策フィルターは、受信メールと送信メールの両方で機能します。 どちらの場合も、管理者がこの保護をより適切に構成することができます。

Phising フィルターは、Office 365 では既定で有効になっていますが、より適切に構成されている必要があります。 EOP でフィッシング対策を使用することをお勧めします。

### <a name="anti-spam"></a>スパム対策

|セキュリティ機能の名前  |推奨 |性  |Comment  |
|---------|---------|---------|---------|
|検疫の保存期間    |   はい      |     はい    |   30 日   |
|エンドユーザーのスパム通知の頻度   |   はい      |     はい    |   3 日間   |
|ゼロ時間自動削除を有効にする   |   はい      |     はい    |   True  |
|スパム検出アクションをに送信する必要があります。 | JMF | Quarantine | - |
|信頼度の高いスパム検出アクションを送信する必要がある | Quarantine | Quarantine| - |
|一括検出アクションをに設定する必要があります | JMF | Quarantine | - |
|バルクメールしきい値をに設定する | シックス | 2/4 | - |
|安全のヒントを有効にする必要がある| True | True | - |
|エンドユーザーのスパム通知を有効にする| True | False | - |
|許可された送信者 | なし | なし | - |
|許可される送信者ドメイン | なし | なし | - |
|受信拒否リスト | なし | なし | - |
|受信拒否ドメイン | なし | なし | - |
|送信スパムポリシーの RRL | 500 | 500 | - |

推奨およびアグレッシブレベルの両方で**オフ**にすることをお勧めします。

|セキュリティ機能の名前  |
|---------|
|IncreaseScoreWithImageLinks|
|IncreaseScoreWithNumericIps|
|IncreaseScoreWithRedirectToOtherPort|
|IncreaseScoreWithBizOrInfoUrls|
|MarkAsSpamEmptyMessages|
|MarkAsSpamJavaScriptInHtml|
|MarkAsSpamFramesInHtml|
|MarkAsSpamObjectTagsInHtml|
|MarkAsSpamEmbedTagsInHtml|
|MarkAsSpamFormTagsInHtml|
|MarkAsSpamWebBugsInHtml|
|MarkAsSpamSensitiveWordList|
|MarkAsSpamFromAddressAuthFail|
|MarkAsSpamNdrBackscatter|

推奨されるレベルとアグレッシブ**レベルの両方について**推奨されます。

|セキュリティ機能の名前  |
|---------|
|MarkAsSpamSpfRecordHardFail|
|MarkAsSpamBulkMail|

### <a name="anti-malware"></a>マルウェア対策

|セキュリティ機能の名前  |推奨 |性  |Comment  |
|---------|---------|---------|---------|
|内部ソースのマルウェア通知を構成する |はい |はい |- |
|マルウェア検出の外部送信者に通知することを無効にする |はい |はい |- |
|疑わしいファイルの種類をブロックするために "一般的な添付ファイルの種類のフィルター" を使用する | はい |はい |- |
|マルウェアの ZAP |True |True |- |
|マルウェアアクション |Block |Block |- |

### <a name="anti-phishing"></a>フィッシング対策

|セキュリティ機能の名前  |推奨 |性  |Comment  |
|---------|---------|---------|---------|
|ゼロ時間自動削除を有効にする-フィッシング| True | True | - | 
|フィッシング検出アクションをに設定する必要があります。 | 検疫-要求 | 検疫-管理者 | - |
|精度の高いフィッシングの検出アクションをに設定する必要があります。 | 検疫-管理者 | 検疫-管理者 | - |
|EnableMailboxIntelligence | True | True | - |
|Enablesimilarユーザーヒント Etytips | True | True | - |
|Enablesimilardomainssaf Etytips | True | True | - |
|EnableUnusualCharactersSafetyTips | True | True | - |
|され |NoAction |Block | - |
|MailboxIntelligenceProtectionAction |NoAction |Block | - |
|TargetedDomainProtectionAction |NoAction |Block | - |
|AuthenticationFailAction |MoveToJmf |Quarantine | - |
|AntiSpoofEnforcementType |高 |高 | - |
|Enableauthenticationsaf Etytip |False |True | - |
|EnableAntiSpoofEnforcement |True |True | - |
|Enable/認証 Atedsender |True |True | - |
|Enableauthenticationsoftpass Saf Etytip |False |True | - |
|TreatSoftPassAsAuthenticated |True |False | - |
|EnableSuspiciousSafetyTip |True |True | - |

## <a name="office-365-advanced-threat-protection-atp-security"></a>Office 365 Advanced Threat Protection (ATP) のセキュリティ

前述したように、E3 サブスクリプションで Office 365 ATP プラン1を追加するか、完全に実現された ATP プラン2を追加することをお勧めします。 高度なフィッシング対策は、その理由の1つです。 [有効] 既定では、運用のためのポリシーを使用して、フィッシング対策を構成***する必要があり***ます。 フィッシング対策ポリシーの構成を忘れると、ユーザーはリスクにさらされることになります。そのためには、ATP のサブスクリプションを追加した後に、手順2を実行してください。

> [!IMPORTANT]
>  E5 サブスクリプションを使用している場合は、現在、 [ATP プラン 2](https://products.office.com/exchange/advance-threat-protection)があります。 [ATP の新機能](https://review.docs.microsoft.com/microsoft-365/security/office-365-security/whats-new-in-office-365-atp?branch=oatp-newstuff)を確認するには、このリンクをクリックしてください。

### <a name="advanced-anti-phishing"></a>高度なフィッシング対策

フィッシングとは、クレジットカード番号、コンピューターまたはデバイスの pin またはパスワードなどの個人情報を盗むことを目的として、著名な企業または個人としてのマスカレードを試みることです。 フィッシングには次のようなものがあります。

- **スプーフィング**、なりすまし者は、ドメイン内の特定のターゲットに代わってメールを送信しようとします (たとえば、ellar@2020contoso.com のメールを送信しようとしている場合は、電子メールの認証方法を使用して阻止できます)。 

- **偽装**。送信者が視覚的に似ている (または見える) 送信元のドメインまたはユーザー名であることを示すメールを受信します。 無効な出演者は、特定のユーザー名を模倣するか、または pretends をターゲットドメインからメールを送信します。 Pretense ドメイン: ellar @ 2020 | itware。次に、pretense ユーザー: ellαr @ 2020litware (次の例のドメイン名とユーザー名をよく調べて、ドメインとユーザー偽装をキャッチします) を示します。

EOP に Office 365 ATP サブスクリプションを追加した場合は、次の構成を必ず設定してください。

|セキュリティ機能の名前  |推奨 |性  |Comment  |
|---------|---------|---------|---------|
|詳細なフィッシングしきい値をに設定します。 | pbm-2 | 2/4 | - |
|偽装防止保護を有効にする | はい | はい | - |
|スパム対策ポリシーでメールボックスインテリジェンスを有効にする | はい | はい | - |
|メールボックスインテリジェンスベースの偽装保護を有効にする | はい | はい | - |
|ドメイン偽装アクション | JMF | Quarantine | - |
|ユーザー偽装アクション | JMF | Qurantine | - |
|メールボックスインテリジェンスベースの偽装保護アクション |部  |JMF | - |

### <a name="safe-links-and-safe-attachments"></a>安全なリンクと安全な添付ファイル

 ATP には、安全な添付ファイルと安全なリンクのポリシーが含まれています。これにより、悪意のある添付ファイルを持つ電子メールが配信されないようにしたり、ユーザーが安全でない可能性のある Url に対してクリックや移動

#### <a name="safe-links"></a>安全なリンク

|セキュリティ機能の名前  |推奨 |性  |Comment  |
|---------|---------|---------|---------|
|ATP の安全なリンクは、応答目的でユーザーのクリックを追跡する必要がある |はい |はい |- |
|Office アプリケーションに対して ATP の安全なリンクを有効にする必要がある |はい |はい |- |
|ATP の安全なリンクはドメイン内で有効にする必要があります。 |はい |はい |- |
|ATP の安全なリンクは、疑わしいリンクおよびファイルを指すリンクに対してリアルタイム URL スキャンを適用する必要があります。 |はい |はい |- |
|ATP の安全なリンクは、メッセージを配信する前に、URL のスキャンが完了するのを待機する必要があります。 |はい |はい |- |
<!--
|URLs to block | | | |
|URLs not to wrap | | | |-->

#### <a name="safe-attachments"></a>添付ファイル保護

|セキュリティ機能の名前  |推奨 |性  |Comment  |
|---------|---------|---------|---------|
|ATP の安全な添付ファイルポリシーアクションは、 |Quarantine |Quarantine |- |
|OneDrive、SharePoint、および Teams に対して ATP 保護を有効にする必要がある |はい |はい |- |
<!--
|Allowed file hashes | | | |
|Blocked file hashes | | | |
-->

## <a name="miscellaneous-settings"></a>その他の設定

これらの設定は、上記の特定のカテゴリに必ずしも適合しない機能の範囲をカバーしています。 ここでは、1回限りの設定についても確認できます。

セキュリティ機能の名前  |推奨 |性  |Comment  |
|---------|---------|---------|---------|
|SPF レコードを作成する |はい |はい |- |
|ドメインの DKIM 署名を構成する |はい |はい |- |
|拒否または検疫アクションによるドメインベースのメッセージ報告と準拠 (DMARC) の実装 |action = なし |action = reject | |
|レポートメッセージのアドオンを展開して、疑わしいメールのエンドユーザーのレポートを向上させる |はい |はい |- |
|マルウェアおよびスパムレポートをスケジュールする |はい |はい |- |
|外部ドメインへの自動 fowarding を許可または監視する |- |はい |- |
|統合監査を有効にする必要があります。 |はい |はい |- |
|必要でない場合に IMAP を無効にする必要がある |- |党 |- |
|不要な場合は、POP を無効にする必要があります。 |- |党 |- |
|アプリケーションで不要な場合は、SMTP 認証送信をオフにする必要があります。 |- |党 |- |
|EWS を無効にする必要がある |- |党 |- |
|PowerShell |- |党 |- |
|Sender Policy Framework をハードフェイルオーバーに構成する |-all |-all |- |
|スプーフィングインテリジェンスを使用して、可能な場合には送信者をホワイトリストする |はい |はい |- |
|ディレクトリベースのエッジブロック (DBEB) |有効 |有効 |ドメインの種類 = 権限あり |
