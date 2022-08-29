---
title: Office 365 Message Encryption
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.date: 02/07/2020
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
ms.custom:
- seo-marvel-apr2020
description: 組織内外のユーザー間で暗号化された電子メール メッセージを送受信する方法について説明します。
ms.openlocfilehash: 0501aeb833d41048e6e3f8848f20b3e4b0bc217b
ms.sourcegitcommit: 57e6a8e42b41376c4f4021754c918502bf52d209
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2022
ms.locfileid: "67427116"
---
# <a name="message-encryption"></a>メッセージ暗号化

電子メールは、財務データ、法的契約、社外秘の製品情報、売上レポートや売上見込み、患者の医療情報、顧客や従業員の情報などの機密性の高い情報を交換するためによく使われています。その結果、メールボックスが機密性の高い大量の情報のリポジトリとして使用され、組織にとって情報漏洩が深刻な脅威となる可能性があります。

Office 365 Message Encryption を使用すると、組織は組織内外のユーザーとの間で暗号化されたメール メッセージを送受信できます。 Office 365 Message Encryption は、Outlook.com、Yahoo!、Gmail、およびその他のメール サービスで機能します。 メール メッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。

## <a name="how-message-encryption-works"></a>メッセージ暗号化のしくみ

この記事の残りの部分は、Microsoft Purview Message Encryptionに適用されます。

Microsoft Purview Message Encryptionは、Azure Information Protectionの一部である Microsoft Azure Rights Management (Azure RMS) 上に構築されたオンライン サービスです。 このサービスには、電子メールのセキュリティ保護に役立つ暗号化、ID、承認ポリシーが含まれています。 メッセージを暗号化するには、アクセス許可管理のテンプレートである[転送不可オプション](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)および[暗号化のみ](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)オプションを使用します。

その後、ユーザーはこれらのオプションを使用して電子メール メッセージとさまざまな添付ファイルを暗号化できます。 サポートされている添付ファイルの種類の完全な一覧については、 [電子メール メッセージの IRM の概要に関する記事の「IRM ポリシーがメッセージに添付されたときのファイルの種類」を参照](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)してください。

管理者は、この保護を適用するメール フロー ルールを定義することもできます。 たとえば、特定の受信者宛てのすべてのメッセージや件名行に特定の言葉が含まれるメッセージの暗号化を要求したり、受信者はメッセージのコンテンツのコピーや印刷の禁止を規定したりするルールを作成できます。

以前のバージョンの OME とは異なり、新しい機能は、組織内または Microsoft 365 以外の受信者にメールを送信する場合でも、統合された送信者エクスペリエンスを提供します。 さらに、Outlook 2016またはOutlook on the webで Microsoft 365 アカウントに送信された保護された電子メール メッセージを受け取る受信者は、メッセージを表示するために他の操作を行う必要はありません。 シームレスに動作します。 また、他のメール クライアントやメール サービス プロバイダーを使用している受信者の操作性も向上しました。 詳細については、「[Office 365 の保護されたメッセージについて](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)」および「[保護されたメッセージを開く方法を教えてください](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)」を参照してください。

以前のバージョンの OME とMicrosoft Purview Message Encryptionの違いの詳細な一覧については、「[メッセージ暗号化のバージョンの比較](ome-version-comparison.md)」を参照してください。

暗号化メール フロー ルールに一致するメール メッセージを誰かが送信すると、メッセージは送信される前に暗号化されます。 Outlook クライアントを使用してメールを読み取るすべての Microsoft 365 エンド ユーザーは、送信者と同じ組織にいない場合でも、暗号化された権限で保護されたメールのネイティブのファースト クラスの読み取りエクスペリエンスを受け取ります。 サポートされている Outlook クライアントには、Outlook デスクトップ、Outlook Mac、iOS および Android の Outlook Mobile、Outlook on the web (旧称: Outlook Web App) が含まれます。

暗号化されたメッセージの受信者が、Outlook.com、Gmail、および Yahoo アカウントに送信された暗号化されたメールまたは権限で保護されたメールを受け取る場合は、暗号化されたメッセージ ポータルに送信されるラッパー メールを受け取り、Microsoft アカウント、Gmail、または Yahoo 資格情報を使用して簡単に認証できます。

Outlook 以外のクライアントで暗号化または権限で保護されたメールを読み取るエンド ユーザーは、暗号化されたメッセージ ポータルを使用して、受信した暗号化された権限で保護されたメッセージを表示することもできます。

保護されたメールの送信者が GCC High にあり、受信者が GCC High の外部にある場合 (商用ユーザー、Outlook.com ユーザー、Gmail などの他のメール プロバイダーのユーザーを含む) は、受信者にラッパー メールを受信します。 ラッパー メールは、受信者がメッセージを読み取って返信できる暗号化されたメッセージ ポータルに受信者を送信します。 上記以外の場合で、送信者と受信者の両方が GCC High の内部にいる場合は、たとえ受信者が同じ組織に存在していない場合でも、Outlook クライアントを使用してメールを読む受信者には暗号化され権限で保護されたメールでネイティブの、ファーストクラスの読み取り操作が提供されます。 GCC High での操作方法の違いの詳細については、「[OME のバージョンを比較する](ome-version-comparison.md)」を参照してください。

OME を使用して暗号化できるメッセージおよび添付ファイルのサイズ制限の詳細については、 「[Exchange Online の制限](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)」を参照してください。

## <a name="how-microsoft-purview-advanced-message-encryption-works-on-top-of-microsoft-purview-message-encryption"></a>Microsoft Purview Advanced Message Encryption がMicrosoft Purview Message Encryption上でどのように機能するか

Microsoft Purview Advanced Message Encryption を使用すると、複数のブランド 化テンプレートを作成して、受信者のメールをきめ細かく制御し、多様な組織構造をサポートするカスタム ブランド エクスペリエンスを作成できます。

Microsoft 365 の高度なメッセージ暗号化は、暗号化されたメールに対する外部受信者のアクセスをより柔軟に制御する必要があるコンプライアンス義務を満たすのに役立ちます。 高度なメッセージ暗号化を使用すると、管理者として、機密情報の種類 (PII、財務、正常性 ID など) を検出する自動ポリシーや、セキュリティで保護された Web ポータルから暗号化された電子メールへのアクセスを期限切れにすることで保護を強化するキーワードを使用して、組織外で共有される機密メールを制御できます。 管理者は、電子メールへのアクセスをいつでも取り消すことで、Web ポータルを介してアクセスされる暗号化された電子メールをさらに制御できます。

メッセージの失効と有効期限は、ユーザーが組織外の受信者に送信する電子メールに対してのみ機能します。 また、受信者は Web ポータル経由でメールにアクセスする必要があります。 受信者がメールを受信するのにポータルを使用するよう、ラッパーを適用するカスタム ブランド テンプレートを設定します。 次に、メール フロー ルールでブランド テンプレートを適用します。 高度なメッセージ暗号化の詳細については、「 [高度なメッセージ暗号化」を](ome-advanced-message-encryption.md)参照してください。

## <a name="defining-rules-for-microsoft-purview-message-encryption"></a>Microsoft Purview Message Encryptionのルールの定義

Microsoft Purview Message Encryptionを有効にする 1 つの方法は、Exchange Online管理者とExchange Online Protection管理者がメール フロー ルールを定義することです。 これらのルールにより、メール メッセージの暗号化が求められる条件が規定されます。 暗号化アクションをルールで設定すると、そのルールの条件を満たすすべてのメッセージが送信前に暗号化されます。

メール フロー ルールは柔軟であるため条件を組み合わせることができ、1 つのルールで特定のセキュリティ要件を満たすことができます。 たとえば、指定したキーワードを含み、外部の受信者に宛てられたすべてのメッセージを暗号化するルールを作成できます。 Microsoft Purview Message Encryptionでは、暗号化された電子メールの受信者からの返信も暗号化されます。

Microsoft Purview Message Encryptionを利用するメール フロー ルールを作成する方法の詳細については、「[メール メッセージを暗号化するメール フロー ルールを定義する」を](define-mail-flow-rules-to-encrypt-email.md)参照してください。

## <a name="get-started-with-the-microsoft-purview-message-encryption"></a>Microsoft Purview Message Encryptionの使用を開始する

組織内でMicrosoft Purview Message Encryptionの使用を開始する準備ができたら、「[Microsoft Purview Message Encryptionのセットアップ](set-up-new-message-encryption-capabilities.md)」を参照してください。

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>暗号化されたメール メッセージの送信、表示、および返信

Microsoft Purview Message Encryptionを使用すると、ユーザーは Outlook とOutlook on the webから暗号化された電子メールを送信できます。 さらに、管理者は Microsoft 365 でメール フロー ルールを設定して、キーワード一致やその他の条件に基づいて電子メールを自動的に暗号化できます。

組織にいる暗号化されたメッセージの受信者は、Outlook for PC、Outlook for Mac、Outlook on the web、Outlook for iOS、Android 用 Outlook など、任意のバージョンの Outlook でこれらのメッセージをシームレスに読み取ることができるでしょう。 他の電子メール クライアントで暗号化されたメッセージを受信するユーザーは、暗号化されたメッセージ ポータルでメッセージを表示できます。

暗号化されたメッセージを送信して表示する方法の詳細については、これらの記事を参照してください。

|関連記事|記事の対象となるユーザーの種類|
|:-----|:-----|
|[Office 365 の保護されたメッセージについて](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|暗号化されたメッセージの仕組みや利用できるオプションについて詳しく知りたいエンド ユーザー。|
|[保護されたメッセージを開く方法を教えてください](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|自分宛てに送信された保護されたメッセージを読みたいエンド ユーザー。 この記事には、Gmail や Yahoo! などの Microsoft 365 以外のアカウントを含む、複数のバージョンの Outlook とさまざまなメール アカウントのメッセージの読み取りに関する情報が含まれています。 。|
|[Outlook での暗号化されたメッセージの送信、表示、および返信](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)|暗号化されたメッセージの送信、表示、返信を Outlook で行うエンド ユーザー。 組織のメンバーでない場合でも、Outlook で送信された暗号化されたメッセージの通知を受け取ります。 Office 365 から送信された暗号化メッセージを表示して返信する方法については、こちらの記事を参照してください。|
|[デジタル署名または暗号化されたメッセージを送信する](https://support.microsoft.com/office/send-a-digitally-signed-or-encrypted-message-a18ecf7f-a7ac-4edd-b02e-687b05eff547)|暗号化されたメッセージの送信、表示、または返信を Outlook for Mac で行うエンド ユーザー。 この記事では、OME 以外の暗号化方法 (S/MIME など) の使用についても説明します。|
|[暗号化されたメッセージを Android デバイスで表示する](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|Office 365 Message Encryption で暗号化されたメッセージを Android デバイスで受信したエンド ユーザーは、無料の OME Viewer アプリを使用してメッセージを表示し、暗号化された返信を送信できます。 この記事では、その方法について説明します。|
|[iPhone または iPad で暗号化されたメッセージを表示する](https://support.microsoft.com/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)|Office 365 Message Encryption で暗号化されたメッセージを iPhone または iPad で受信したエンド ユーザーは、無料の OME Viewer アプリを使用してメッセージを表示し、暗号化された返信を送信できます。 この記事では、その方法について説明します。|
||
