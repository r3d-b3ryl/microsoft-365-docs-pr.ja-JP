---
title: ゼロアワー自動消去 - スパムまたはマルウェアからの保護
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 11/21/2019
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.assetid: 96deb75f-64e8-4c10-b570-84c99c674e15
ms.collection:
- M365-security-compliance
description: ゼロ時間自動削除 (ZAP) は、ユーザーの受信トレイに既に配信されているスパムまたはマルウェアを含むメッセージを検出し、その悪意のあるコンテンツを無害にする電子メール保護機能です。 これは、検出された悪意のあるコンテンツの種類によってどのような違いがありますか。
ms.openlocfilehash: 6616281a98487c7edd7ca7721ade9a8510f6a21f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41597961"
---
# <a name="zero-hour-auto-purge---protection-against-spam-and-malware"></a>ゼロアワー自動消去 - スパムまたはマルウェアからの保護

## <a name="overview"></a>概要

ゼロ時間自動削除 (ZAP) は、ユーザーの受信トレイに既に配信されているフィッシング、スパム、またはマルウェアを含むメッセージを検出し、悪意のあるコンテンツを表示する電子メール保護機能です。 これは、検出された悪意のあるコンテンツの種類によってどのような違いがありますか。 メールの内容、Url、または添付ファイルのため、メールを zapped することができます。

ZAP は、Exchange Online メールボックスを含む Office 365 サブスクリプションに含まれている既定の Exchange Online Protection で利用できます。

## <a name="how-zap-works"></a>ZAP のしくみ

Office 365 は、毎日スパム対策エンジンとマルウェア署名をリアルタイムで更新します。 ただし、ユーザーが配信された後にコンテンツが weaponized されている場合を含め、さまざまな理由で、ユーザーは引き続き悪意のあるメッセージを受信トレイに配信する可能性があります。 ZAP は、継続的に Office 365 スパムおよびマルウェア署名の更新を監視することによって解決します。 ZAP は、既にユーザーの受信トレイにある配信済みメッセージを見つけて削除することができます。

ZAP アクションは、メールボックスユーザーにとってシームレスです。電子メールメッセージが移動された場合は通知されません。 

許可リスト、[メールフロールール](use-transport-rules-to-configure-bulk-email-filtering.md)(トランスポートルールとも呼ばれます)、およびエンドユーザールールまたは追加フィルターは、ZAP より優先されます。

### <a name="malware-zap"></a>マルウェアの ZAP

新たに検出されたマルウェアの場合、ZAP は添付ファイルを含むメッセージ全体をマルウェア検疫に移動します。 メッセージは、メールの開封状況に関係なく移動されます。 動的配信スキャンプロセスでメッセージに対するマルウェア信号を受け取った場合、ZAP はメッセージに対して [迷惑メールに移動] アクションを実行します。 その後、動的配信が配信スキャンの時間を終了し、適切なアクションを実行できるようになります。

マルウェアの ZAP は、マルウェアポリシーで既定で有効になっています。 Exchange Online PowerShell または Exchange Online Protection PowerShell で[new-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)コマンドレットの*zapenabled*パラメーターを使用して、マルウェアの ZAP を無効にすることができます。 セキュリティ/コンプライアンスセンターでマルウェアポリシーを編集することによって、マルウェアの ZAP を有効または無効にすることもできます。

### <a name="phish-zap"></a>フィッシング ZAP

配信後にフィッシングとして識別されるメールの場合、ZAP は、メールの読み取り状態に関係なく、特定のユーザーを対象とするスパムポリシーに従って処理を行います。 [Policy フィッシング] アクションが [操作を行わ*ない*(追加する X-ヘッダー、件名の変更、アクションなし)] に設定されている場合、ZAP はメールに対して何のアクションも実行しません。 フィッシングアクションが迷惑メールに移行するように設定されている場合、ZAP はメッセージをユーザーの受信トレイの迷惑メールフォルダーに移動します。 **その他のフィッシングアクション (リダイレクト、削除、検疫) ZAP では、メッセージはフィッシング検疫に移動され**ます。 構成の要件と除外については、以下を参照してください。 ここでは[、スパムフィルターポリシーを構成](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies)する方法について説明します。

スパムポリシーでは、フィッシング ZAP が既定で有効になっています。 フィッシング ZAP[は、EOP コマンドレットの](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) *PhishZapEnabled*パラメーターを使用して無効にすることができます。

### <a name="spam-zap"></a>スパム ZAP

配信後にスパムとして識別されるメールの場合、ZAP は、メッセージが未読の場合にのみ、特定のユーザーを対象としたスパムポリシーに従って処理を行います。  [迷惑メールの処理] アクションが行われない ([X-ヘッダーの追加]、[件名の変更]、[アクションなし)] の順に設定した場合、ZAP はメールに対して何のアクションも実行しません。 スパムアクションが迷惑メールに移行するように設定されている場合、ZAP はメッセージをユーザーの受信トレイの迷惑メールフォルダーに移動します。 **その他のスパム操作 (リダイレクト、削除、検疫) ZAP では、メッセージはスパム検疫に移動され**ます。 構成の要件と除外については、以下を参照してください。 ここでは[、スパムフィルターポリシーを構成](https://docs.microsoft.com//office365/securitycompliance/configure-your-spam-filter-policies)する方法について説明します。

スパム ZAP は、スパムポリシーでは既定で有効になっています。 Exchange Online PowerShell または Exchange Online Protection PowerShell で[set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy)コマンドレットの*SpamZapEnabled*パラメーターを使用して、スパム ZAP を無効にすることができます。

### <a name="phish-and-spam-zap-requirements-exclusions-and-notices"></a>フィッシングおよびスパム ZAP の要件、除外、および通知

> [!IMPORTANT]
> フィッシングとスパム ZAP の両方を制御する前の*Zapenabled*コマンドレットパラメーターは、 **2020 年2月1日に廃止**されます。 ZapEnabled パラメーターを使用するスクリプトを記述した場合は、SpamZapEnabled と PhishZapEnabled を使用するように更新することをお勧めします。 移行期間では、3つすべてのパラメーター (ZapEnabled、PhishZapEnabled、および SpamZapEnabled) がコマンドレットで使用できるようになります。 UI または PowerShell を使用して明示的に設定されるまで、PhishZapEnabled と SpamZapEnabled は ZapEnabled パラメーターから継承した値を表示します。 新しいパラメーターが設定されると、ZapEnabled パラメーターから継承されなくなります。 使用されなくなった場合、ZapEnabled が PhishZapEnabled または SpamZapEnabled プロパティに影響を与えることはありません。また、ZapEnabled はコマンドレットのパラメータリストから削除されます。

ZAP は、動的配信スキャンのプロセスに含まれるすべてのメッセージ、または既にマルウェアが verdict に置き換えられた添付ファイルを持つ検疫に移動しません。 これらの種類のメッセージに対してフィッシングまたはスパムのシグナルを受信し、Spam policy/フィッシングアクションを実行するように設定されている場合 ([迷惑メールに移動] に移動)、ZAP は既定で [迷惑メールに移動] アクションになります。 メッセージに対して [迷惑メールに移動] アクションを使用するには、ユーザーは既定の迷惑メール設定を使用して、迷惑メール保護を有効にする必要があります。 (Outlook のユーザーオプションの詳細については[、「迷惑メールフィルターの保護レベルを変更](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)する」を参照してください)。

## <a name="how-to-see-if-zap-moved-your-message"></a>ZAP がメッセージを移動したかどうかを確認する方法

ZAP がメッセージを移動したかどうかを確認するには、[脅威保護状態レポート](view-email-security-reports.md#threat-protection-status-report)または[脅威エクスプローラー (およびリアルタイム検出)](threat-explorer.md)のいずれかを使用できます。 システムアクションとして、ZAP が exchange メールボックス監査ログに記録されないことに注意してください。 
 
## <a name="disable-zap"></a>ZAP を無効にする

Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。 Exchange Online Protection PowerShell に接続するには、「 [Exchange Online protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。

### <a name="disable-malware-zap"></a>マルウェアの無効化 * *

[New-malwarefilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)コマンドレットでは、Exchange online powershell または Exchange Online Protection Powershell で*zapenabled*パラメーターを使用して、マルウェアの ZAP を無効にすることができます。 セキュリティ/コンプライアンスセンターでマルウェアポリシーを編集することによって、マルウェアの ZAP を有効または無効にすることもできます。

この例では、"Test" という名前のマルウェアフィルターポリシーの ZAP を無効にします。

```Powershell
Set-MalwareFilterPolicy -Identity Test -ZapEnabled $false
```

構文とパラメーターの詳細については、「[Set-MalwareFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-malwarefilterpolicy)」を参照してください。

### <a name="disable-phish-zap-and-spam-zap"></a>フィッシング ZAP とスパム ZAP を無効にする

O365 テナントまたはユーザーのセットに対してフィッシングおよびスパム ZAP を無効にするに[は、EOP コマンドレットの](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy) *PhishZapEnabled*パラメーターと*SpamZapEnabled*パラメーターを使用します。

次の例では、"Test" という名前のコンテンツフィルターポリシーに対してフィッシングおよびスパム ZAP が無効になっています。

```Powershell
Set-HostedContentFilterPolicy -Identity Test -PhishZapEnabled $false -SpamZapEnabled $false
```

構文およびパラメーターの詳細については、「 [set-hostedcontentfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/Set-HostedContentFilterPolicy)」を参照してください。

## <a name="faq"></a>FAQ

### <a name="what-happens-if-a-legitimate-message-is-moved-to-the-junk-mail-folder"></a>正当なメッセージが迷惑メールフォルダーに移動された場合はどうなりますか。

誤[検知](prevent-email-from-being-marked-as-spam.md)の通常のレポートプロセスに従う必要があります。 メッセージが [受信トレイ] から [迷惑メール] フォルダーに移動されるのは、サービスがスパムまたは悪意のあるメッセージであると判断した場合のみです。

### <a name="what-if-i-use-the-office-365-quarantine-instead-of-the-junk-mail-folder"></a>迷惑メールフォルダーではなく、Office 365 検疫を使用している場合はどうなりますか?

ZAP は、スパム対策ポリシーのフィッシングおよびスパムの処理設定の構成に従って処理を実行します。 マルウェア、フィッシング、スパム ZAP の詳細については、上記を参照してください。

### <a name="what-if-i-have-a-custom-mail-flow-rule-block-allow-rule"></a>カスタムメールフロールール (ブロック/許可ルール) を持っている場合

管理者によって作成されたルール (メールフロールール) またはブロックと許可ルールが優先されます。 このようなメッセージは、機能の条件から除外されるので、メールフローはルールの処理 (ブロック/許可ルール) に従います。

### <a name="what-if-a-message-is-moved-to-another-folder-eg-inbox-rule"></a>メッセージが別のフォルダー (たとえば、受信トレイルールなど) に移動した場合はどうなりますか。

この場合、ZAP は、メッセージが削除されているか、迷惑メールにある場合を除き、この場合でも動作します。

### <a name="does-zap-change-the-email-header"></a>電子メールのヘッダーを ZAP に変更しますか?

ZAP アクションでは、電子メールのヘッダーに対して変更は行われません。

### <a name="how-does-zap-affect-mailboxes-on-hold"></a>ZAP がメールボックスを保留にする方法

ZAP はメールボックスから保留中のメッセージを削除しないので、メッセージに対して "検疫に移動" アクションを実行することはありません。 ポリシーによって指定されている場合、メッセージは引き続き迷惑メールフォルダーに移動されます。 

[メールボックス保持の詳細については、ここをクリックしてください。](https://docs.microsoft.com/exchange/policy-and-compliance/holds/holds?view=exchserver-2019)

## <a name="related-topics"></a>関連項目

[Office 365 の電子メールのスパム対策保護](anti-spam-protection.md)

[検出漏れの問題を防止するために Office 365 スパム フィルターを使用して迷惑メールをブロックする](reduce-spam-email.md)
