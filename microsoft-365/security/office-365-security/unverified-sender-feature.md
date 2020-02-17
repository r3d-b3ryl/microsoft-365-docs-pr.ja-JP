---
title: 未確認の送信者
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: フィッシングメッセージがメールボックスに到達しないようにするため、Outlook.com および web 上の Outlook では、送信者が本人であることを確認し、疑わしいメッセージを迷惑メールとしてマークします。
ms.openlocfilehash: 513a45594dd41db56abe143ea6edca7074539d2f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42082009"
---
# <a name="unverified-sender"></a>未確認の送信者

> [!NOTE]
> これらの更新プログラムは現在ロールアウトされており、すべてのユーザーが使用できるとは限りません。 この機能は、エンタープライズ Outlook.com およびエンタープライズ Outlook Win32 デスクトップユーザーがサポートされています。 現在、コンシューマーの Office 365 ユーザーは使用できません。

フィッシングメッセージがメールボックスに到達しないようにするため、Office 365 は、送信者が本人であることを確認し、疑わしいメッセージを迷惑メールとしてマークします。

> [!IMPORTANT]
> メッセージがフィッシング詐欺メールとしてマークされている場合は、ページの上部に警告が表示されますが、メッセージ内のすべてのリンクを開くことができます。

## <a name="how-can-i-identify-a-suspicious-message-in-my-inbox"></a>受信トレイ内の疑わしいメッセージを特定するには、どうすればよいですか。

Outlook では、メッセージの送信者が識別できない場合や、id が [差出人アドレスに表示されているものと異なる場合に、インジケーターが表示されます。

## <a name="you-see-a--in-the-sender-image"></a>送信者の画像に '? ' が表示される

Office 365 が電子メール認証手法を使用して送信者の身元を確認できない場合は、送信者画像に '? ' が表示されます。

![メッセージが検証に合格しませんでした](../../media/message-did-not-pass-verification.jpg)

認証に失敗したすべてのメッセージが悪意のあるものであるとは限りません。 ただし、送信者を認識しない場合は、認証されないメッセージの操作について注意する必要があります。 または、通常は送信者の画像に '? ' が含まれていない送信者を認識したが、突然表示を開始した場合は、送信者がスプーフィングされているという署名になることがあります。

## <a name="how-to-manage-which-messages-receive-the-unverified-sender-treatment"></a>未確認の送信者の処理を受信するメッセージを管理する方法 

Office 365 をご利用のお客様の場合は、Office 365 セキュリティ & コンプライアンスセンターを使用してこの機能を管理できます。

- セキュリティ & コンプライアンスセンターでは、フィッシングポリシーの下にあるスプーフィング対策保護を使用して、グローバルまたはセキュリティ管理者がこの機能を有効または無効にすることができます。 また、Exchange Online PowerShell で**get-antiphishpolicy**コマンドレットを使用することもできます。 詳細については、「 [Office 365 のフィッシング対策保護](anti-phishing-protection.md)」および「 [get-antiphishpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-antiphishpolicy)」を参照してください。

    ![グラフィックインターフェイスで認証されていない送信者を編集する。](../../media/unverified-sender-article-editing-unauthenticated-senders.jpg)

- 管理者が誤検知を識別し、送信者が未確認の送信者による処理を受信しないようにした場合は、次のいずれかの操作を行って、スプーフィングインテリジェンススプーフィング許可リストに送信者を追加することができます。

  - スプーフィングインテリジェンスの洞察を通じてドメインペアを追加します。 詳細については、「[チュートリアル: スプーフィングインテリジェンスの洞察](walkthrough-spoof-intelligence-insight.md)」を参照してください。

  - Exchange Online PowerShell で**get-phishfilterpolicy**コマンドレットを使用して、ドメインのペアを追加します。 詳細については、「 [get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-phishfilterpolicy) 」および「 [set UP Office 365 ATP フィッシング詐欺防止」および「設定](set-up-anti-phishing-policies.md)」を参照してください。

また、メッセージがメールフロールール (トランスポートルールとも呼ばれる) または安全なドメインリスト (スパム対策ポリシー) によって受信トレイに配信された場合、未検証の送信者の処理は適用されません。

## <a name="how-to-manage-the-via-tag"></a>' Via ' タグを管理する方法 

Office 365 をご利用のお客様の場合は、Office 365 セキュリティ & コンプライアンスセンターを使用してこの機能を管理できます。これは、未検証の送信者の処理を管理する方法と同じです。 スプーフィングのスプーフィング許可リストに送信者を追加した場合、' via ' 処理は適用されません。

## <a name="frequently-asked-questions"></a>よく寄せられる質問

### <a name="what-criteria-does-outlookcom-and-outlook-win32-desktop-use-to-add-the--and-the-via-properties"></a>Outlook.com と Outlook Win32 デスクトップで、'? ' および ' via ' プロパティを追加するために使用する条件とは何ですか。

送信者イメージの '? ' の場合: Outlook.com では、メッセージが SPF 認証または DKIM 認証のいずれかを通過し、dmarc パスを受け取るか、または Office 365 スプーフィングインテリジェンスからのコンポジット認証パスを受け取ることが要求されます。 詳細については、「 [Set UP SPF In office 365](set-up-spf-in-office-365-to-help-prevent-spoofing.md) 」を参照して、スプーフィングを防止し、 [Dkim を使用して office 365 のカスタムドメインから送信される送信電子メールを検証](use-dkim-to-validate-outbound-email.md)します。

Via タグの場合: From アドレスのドメインが DKIM シグネチャまたは SMTP メールのドメインと異なる場合、Outlook.com は、この2つのフィールドのいずれかにドメインを表示します (DKIM シグネチャを優先します)。

### <a name="how-do-i-remove-the--without-utilizing-the-spoof-intelligence-spoof-allow-list"></a>スプーフィングインテリジェンススプーフィング許可リストを利用せずに '? ' を削除するには、どうすればよいですか?

送信者の画像の '? ' の場合は、送信者として、SPF または DKIM のいずれかを使用してメッセージを認証する必要があります。

Via タグ: 送信者としての場合は、DKIM 署名のドメインまたは SMTP メールが、From アドレスのドメインと同じかサブドメインのものであることを確認する必要があります。

### <a name="do-outlookcom-and-outlook-win32-desktop-show-this-for-every-message-that-doesnt-pass-authentication"></a>Do Outlook.com and Outlook Win32 デスクトップ認証を通過しないすべてのメッセージに対してこのメッセージを表示するかどうか。

必ずしもそうではありません。 Office 365 では、送信者を認証するために、メッセージ内に他のプロパティがある場合があります。

## <a name="related-topics"></a>関連項目

[Outlook.com メールアカウントを保護する](https://support.office.com/article/a4f20fc5-4307-4ece-8231-6d4d4bd8a9ba)

[Outlook.com でのフィッシングまたはスプーフィングに対処する](https://support.office.com/article/0d882ea5-eedc-4bed-aebc-079ffa1105a3)

[Outlook on the web で迷惑メールおよびスパムをフィルター処理する](https://support.office.com/article/db786e79-54e2-40cc-904f-d89d57b7f41d)
