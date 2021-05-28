---
title: EOP の機能
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
ms.assetid: 599b8048-1056-457b-aae4-c063138fd319
description: 次の表は、Exchange Online Protection (EOP) でホストされた電子メール フィルタリング サービスで使用可能な機能の一覧です。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 62530a7c5da7ab0b7fd0e8415c8c366a1caafdda
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/28/2021
ms.locfileid: "52696456"
---
# <a name="eop-features"></a>EOP の機能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)

次の表に、電子メール フィルター サービス (EOP) でExchange Online Protection機能の一覧を示します。

> [!TIP]
> ビジネス[Microsoft 365のロードマップは](https://www.microsoft.com/microsoft-365/roadmap?filters=O365)、今後の新機能に関する情報を見つけ出す良いリソースです。 異なる EOP サブスクリプション プランで使用可能な機能のより広範な説明については、「[Exchange Online Protection サービスの説明](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)」を参照してください。

<br>

****

|機能|説明|
|---|---|
|**マルウェア対策保護**||
|マルウェア対策保護の複数のエンジン|複数のマルウェア対策エンジンは、常にお客様を自動的に保護します。|
|Always-on マルウェア フィルター|マルウェア フィルターを無効にできない。 一貫した、厳しい水準の保護をすべてのお客様に提供することは、お客様の電子メール メッセージ環境の保護に必要な綿密な防御戦略に必要不可欠であると考えています。 そのため、マルウェア フィルタリングはすべてのお客様に対して自動的に有効になっています。|
|メッセージ本文と添付ファイルのマルウェア検査|このサービスは、メッセージ本文とすべての添付ファイルのアクティブなペイロードにマルウェアがないか検査します。|
|スパイウェア対策保護|マルウェア対策保護には、ウイルス対策保護およびスパイウェア対策保護が含まれます。|
|マルウェア フィルター ポリシー|すべての組織には、すべての受信者に適用される既定のスパム対策ポリシーがあります。 詳細については、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタムマルウェア対策ポリシーを作成できます。 カスタム ポリシーは、既定のポリシーの前に常に適用されますが、カスタム ポリシーが適用される順序を変更できます。 <p> マルウェア対策ポリシーでは、次の設定を構成できます。 <ul><li>**一般的な添付ファイル フィルター**: 常にマルウェアと推定されるファイルの種類のカスタマイズされたリストを有効にする。</li><li>**マルウェアの ZAP**: 配信されたマルウェア メッセージをさかのぼって検疫します。 詳細については、「ゼロ時間自動削除[(ZAP)」を参照Exchange Online。](zero-hour-auto-purge.md)</li><li>**受信者通知**: メッセージをサイレント検疫するか、メッセージを検疫し、標準テキストまたはカスタム テキストを含む単一のテキスト ファイルに置き換えられたすべての添付ファイルでメッセージを配信します。</li><li>**送信者通知**: メッセージがマルウェアとして検出された送信者に通知します。</li><li>**管理者通知**: 内部または外部の送信者からのメッセージがマルウェアとして検出された場合に管理者に通知します。</li></ul> <p> 詳細については、「マルウェア対策ポリシー [の構成」を参照してください](configure-anti-malware-policies.md)。|
|**フィッシング対策保護**||
|フィッシング対策保護|EOP は、既知のスパム送信者によって使用されるドメインの一覧を使用します。|
|スプーフィング対策保護|EOP のフィッシング対策保護には、スプーフィング対策の保護が含まれます。 詳細については、「スプーフィング [対策の保護」を参照してください](anti-spoofing-protection.md)。 <p> Microsoft Defender for Office 365フィッシング対策保護には、偽装保護も含まれます。 詳細については、「[Microsoft Defender for Office 365 のフィッシング対策ポリシーにおける排他的な設定](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)」を参照してください。|
|**スパム対策保護**||
|受信スパム検出|詳細については、「スパム対策保護」[を参照Microsoft 365。](anti-spam-protection.md) <p> ハイブリッド環境で必要な追加の手順については、「ハイブリッド環境の迷惑メール フォルダーにスパムを配信するための EOP の構成 [」を参照してください](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)。|
|Backscatter 保護|詳細については [、「Backscatter と EOP」を参照してください](backscatter-messages-and-eop.md)。|
|一括メール フィルタリング|EOP は、スパム対策ポリシーのバルク 苦情 (BCL) しきい値を使用して、バルク メール メッセージをスパムとしてマークします。 詳細については、次のトピックをご覧ください。 <ul><li>[迷惑メールとバルク メールの違い](what-s-the-difference-between-junk-email-and-bulk-email.md)</li><li>[EOP のバルク 苦情レベル (BCL)](bulk-complaint-level-values.md)</li><li>[スパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)</li></ul>|
|悪意のある URL 禁止リスト|EOP では、メッセージ内の既知の悪意のあるリンクを検出するため、いくつかの URL 禁止リストを使用しています。|
|**送信スパム保護**||
|送信スパム検出|送信メールの送信にサービスを使用する場合、送信スパム対策保護は常に有効になります。 詳細については、「送信スパム [保護」を参照してください](outbound-spam-controls.md)。|
|送信スパム ポリシー|すべての組織には、すべての受信者に適用される既定の送信スパム ポリシーがあります。 詳細については、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタムスパム対策ポリシーを作成できます。 カスタム ポリシーは、既定のポリシーの前に常に適用されますが、カスタム ポリシーが適用される順序を変更できます。 <p> スパム対策ポリシーでは、次の設定を構成できます。 <ul><li>**Messsage limts**: 1 時間あたりの外部受信者 [](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits)、1時間あたりの内部受信者、および1 日あたりの最大受信者数のサービスの既定値より低い制限を **設定できます**。</li><li>**制限を超えたユーザー** に対して実行するアクション : ユーザーを 24 時間制限する、ユーザーを解放するまで制限する、または警告のみ。</li><li>**外部メールの自動転送を有効または無効にする**: [詳細](external-email-forwarding.md)</li><li>**メッセージのコピーを管理者に通知または送信する**</li></ul> <p> 詳細については [、「EOP で送信スパム フィルターを構成する」を参照してください](configure-the-outbound-spam-policy.md)。|
|**接続フィルター**||
|接続フィルター ポリシー|組織の IP 許可一覧と IP ブロック 一覧を構成します。 詳細については、「接続フィルター [の構成」を参照してください。](configure-the-connection-filter-policy.md)|
|**スパム管理**||
|スパム対策ポリシー|すべての組織には、すべての受信者に適用される既定のスパム対策ポリシーがあります。 詳細については、組織内の特定のユーザー、グループ、またはドメインに適用されるカスタムスパム対策ポリシーを作成できます。 カスタム ポリシーは、既定のポリシーの前に常に適用されますが、カスタム ポリシーが適用される順序を変更できます。 <p> スパム対策ポリシーでは、次の設定を構成できます。 <ul><li>**スパム フィルターの評決** アクション : メッセージが検出されると、その評決に基づいてアクションを実行 (削除、迷惑メール フォルダーへの移動、検疫など) に構成できます。</li><li>**高度なスパム フィルター (ASF) の設定**: これらの設定については、「EOP の高度なスパム フィルター [(ASF) 設定」を参照してください。](advanced-spam-filtering-asf-options.md)</li><li>**フィッシングとスパムの ZAP**: 配信されたメッセージを迷惑メール フォルダーにさかのぼって検疫または移動します。 詳細については、「ゼロ時間自動削除[(ZAP)」を参照Exchange Online。](zero-hour-auto-purge.md)</li><li>**エンドユーザーのスパム通知を有効にする**: [エンド ユーザーのスパム通知の詳細] を参照してください。(use-spam-notifications-to-release-and-report-quarantined-messages.md)</li>**許可およびブロック** された送信者とドメイン : これらのリストを安全に使用する方法の重要な情報については、「[](create-safe-sender-lists-in-office-365.md)差出人セーフ リストの作成」および「受信拒否リストの作成」を [参照してください](create-block-sender-lists-in-office-365.md)。</li><li>**国際スパム設定**: 言語または送信元の国に基づいてメッセージをブロックします。</li></ul> <p> 詳細については、「[スパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。|
|Web 上のOutlookまたはOutlook経由でスパムを管理する (以前は Outlook Web App)|ユーザーと管理者は、個人用の差出人セーフ リストとブロックされた送信者リストを、ユーザーのメールボックスExchange Onlineできます。 詳細については、「迷惑メールの[設定について」を参照Outlook。](configure-junk-email-settings-on-exo-mailboxes.md#about-junk-email-settings-in-outlook) <p> EOP を使用してオンプレミスの Exchange メールボックスを保護する場合は、ディレクトリ同期を使用して、これらの設定がサービスに確実に同期されます。 詳しくは、「[ディレクトリ同期を使用してメール ユーザーを管理する](/exchange/standalone-eop/manage-mail-users-in-eop#synchronize-directories-with-azure-active-directory-connect-aad-connect)」 を参照してください。|
|誤検知と誤検知を Microsoft に報告します。|詳細については、「[メッセージとファイルを Microsoft に報告する](report-junk-email-messages-to-microsoft.md)」を参照してください。|
|検疫ポータルでメッセージを表示、検索、および管理します。|詳細については [、「EOP で検疫済](manage-quarantined-messages-and-files.md) みメッセージとファイルを管理者として管理する」または「検疫済みメッセージをユーザーとして検索して解放する」 [を参照してください](find-and-release-quarantined-messages-as-a-user.md)。|
|スパム検疫済みメッセージ ヘッダーの表示|検疫でメッセージ ヘッダーを表示した後、ヘッダー テキストをコピーしてメッセージ ヘッダー アナライザー[](https://mha.azurewebsites.net/)に貼り付け、メッセージに何が起こったのかを確認できます。|
|**メール ルーティングとコネクタ**||
|
|条件付きメール ルーティング|詳細については、「[シナリオ: Exchange Online での条件付きメール ルーティング](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)」を参照してください。|
|便宜的な TLS または強制 TLS|<ul><li>日和見 TLS は TLS 接続を試行しますが、TLS 接続が失敗した場合は SMTP 接続を使用します。</li><li>強制 TLS は TLS 接続を強制します。つまり、TLS 接続が失敗した場合、メッセージは拒否されます。</li></ul> <p> TLS、セキュリティ、およびコネクタの詳細については、「[Set up connectors for secure mail flow with a partner organization](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-for-secure-mail-flow-with-a-partner)」をご覧ください。|
|地域ルーティング (特定の地域へのメール フローの制限)|詳細については [、「EOP データセンター」を参照してください](exchange-online-protection-overview.md#eop-datacenters)。|
|SMTP 接続チェック ツール|このツールを使用してメール フローをテストする方法の詳細については、「Test mail flow by validating your Microsoft 365[コネクタ」を参照してください](/exchange/mail-flow-best-practices/test-mail-flow)。|
|一致サブドメイン|受け入れドメインのサブドメイン間のメール フローを有効にする方法の詳細については、「EOP のメール フロー」 [を参照してください](mail-flow-in-eop.md)。|
|**メール フロー ルール**||
|EOP のメール フロー ルール|Exchange Online のメール フロー ルール (トランスポート ルールとも呼ばれる) で使用可能なすべての条件、例外、およびアクションは、Exchange Online メールボックスのないスタンドアロン EOP 組織でも使用できます。 メール フロー ルールの詳細については、次のトピックを参照してください。 <ul><li>[メール フロー ルール](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)</li><li>[メール フロー ルールの条件と例外](/exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</li><li>[メール フロー ルールの処理](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)</li></ul>|
|メール フロー ルールのシナリオ|多くのシナリオでは、トランスポート ルールを使用できます。 次に例を示します。 <ul><li>**ポリシー ベースのフィルター処理** とアクション: ドメイン、キーワード、ファイル名、ファイルの種類、件名、メッセージ本文、送信者、受信者、ヘッダー、IP アドレスでフィルター処理できます。</li><li>**テキスト パターンによるフィルター**: メール フロー ルールでは、配列または正規表現を使用してテキストと一致できます。 1 つの文字列または複数の文字列の配列を使用して、アドレス、件名、本文、または添付ファイル名など、多くのメッセージ プロパティと一致させることもできます。</li><li>**ユーザー辞書**: メール フロー ルールには、テキストとキーワードの長いリストを含め、ユーザー辞書と同じ機能を提供できます。</li><li>**ドメインごとのポリシー** ルール : メール フロー ルールの範囲をカスタマイズして、送信者または受信者のドメイン名、IP アドレス範囲、アドレス キーワードまたはパターン、グループ メンバーシップ、その他の条件を一致できます。</li><li>**添付ファイルのスキャン**: メール フロー ルールを作成して、メール添付ファイルのファイル名、拡張子、およびコンテンツをスキャンできます。</li><li>**ポリシー ルール** 通知を送信者に送信する : メッセージを拒否し、[メッセージを拒否する] または [拡張状態コードを使用してメッセージを拒否する] アクションを使用して、配信不可レポート (NDR またはバウンス メッセージとも呼ばれる) を送信者に送信できます。</li><li>**メッセージのリダイレクトまたはコピー**: メール フロー ルールは、リダイレクト、Cc または Bcc による受信者の追加、受信者の追加、その他のオプションの追加が可能です。</li><li>**メッセージをフィルター処理し、メッセージの属性** またはルーティングを変更する: さまざまな条件に基づいてメッセージをフィルター処理し、各メッセージに一連のアクションを適用できます。</li><li>**転送中のメッセージのスパム信頼レベル (SCL) を変更する**</li></ul> <p> 特定のメール フロー ルールシナリオの記事については、「メール フロー [ルールの手順」を参照してください](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-procedures)。|
|**管理**||
|Web ベースの管理|EOP を管理するには、次の管理センターを使用します。 <ul><li>セキュリティ[Microsoft 365センター](/microsoft-365/security/defender/overview-security-center)</li><li>管理[Exchangeセンター](/exchange/exchange-admin-center)</li><li>管理[Microsoft 365センター](/microsoft-365/admin/admin-overview/about-the-admin-center)</li></ul>|
|PowerShell|組織にメールボックスがExchange Online場合は、PowerShell で EOP [Exchange Online管理します](/powershell/exchange/exchange-online-powershell)。 組織にメールボックスがExchange Online場合は、PowerShell で EOP[機能Exchange Online Protection管理します](/powershell/exchange/exchange-online-protection-powershell)。|
|**レポート作成とログ記録**||
|メッセージ追跡|管理者は、サービスを通過する電子メール メッセージをフォローできます。 対象の電子メール メッセージがサービスによって受信、拒否、延期、または配信されたかどうかを判断できます。 したがって、効率良くユーザーの質問に回答したり、メール フローの問題をトラブルシューティングしたり、ポリシーの変更を検証したり、テクニカル サポートに支援を求める必要性を減らしたりできます。 詳細については、「[セキュリティ/コンプライアンス センターでのメッセージ追跡](message-trace-scc.md)」 を参照してください。|
|Web ベースのレポート|セキュリティ センターのメール保護レポートでは、&データが提供されます。 たとえば、検出されるスパムとマルウェアの量、またはメール フロー ルールが一致する頻度を監視できます。 これらの対話式レポートを使用すると、概要データに関する視覚的なレポートを素早く取得し、過去 90 日間の各メッセージの詳細を確認できます。 詳細については、「メール保護レポート [を使用してマルウェア、スパム](/exchange/monitoring/use-mail-protection-reports)、およびルールの検出に関するデータを表示する」を参照してください。|
|監査ログ|詳細については、「監査レポート」[を参照Exchange Online。](/exchange/security-and-compliance/exchange-auditing-reports/exchange-auditing-reports)|
|**サービス レベル アグリーメント (SLA) とサポート**||
|スパム有効性 SLA|\> 99%|
|偽陽性率 SLA|\< 1:250,000|
|ウイルス検出とブロックする SLA|既知のウイルスの 100%|
|月間稼働時間 SLA|99.999%|
|1 日 24 時間、週 7 日の電話および Web テクニカル サポート|EOP ヘルプおよびサポート オプションの詳細については、「[EOP のヘルプとサポート](help-and-support-for-eop.md)」を参照してください。|
|**その他の機能**||
|サーバーの地域冗長グローバル ネットワーク|EOP は、最適な可用性を提供するよう設計された、複数のデータ センターから成る世界規模のネットワーク上で稼働します。詳細については、「[Exchange Online Protection の概要](exchange-online-protection-overview.md)」の「EOP データセンター」セクションを参照してください。  |
|社内サーバーでメールが受信できない場合のメッセージ キュー|遅延中のメッセージは、キューに 1 日残ります。 メッセージの再試行は、受信者のメールシステムから返されたエラーに基づいて行われます。 平均では、5 分ごとにメッセージの送信が再試行されます。 詳細については、「[EOP のキューイング、保留、返送されるメッセージに関する FAQ](eop-queued-deferred-and-bounced-messages-faq.yml)」を参照してください。|
|アドオン サービスとして利用可能な Office 365 Message Encryption|詳細については、「[Office 365 での暗号化](../../compliance/encryption.md)」をご覧ください。|
|
