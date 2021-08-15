---
title: メッセージの暗号化
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 02/07/2020
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.assetid: f87cb016-7876-4317-ae3c-9169b311ff8a
ms.custom:
- seo-marvel-apr2020
description: 組織内外のユーザー間で暗号化された電子メール メッセージを送受信する方法について学習します。
ms.openlocfilehash: 779d23222dd3308ed6464f195cc63ee11da0fc35cf32986c15cc4f7008ac0a97
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53895285"
---
# <a name="message-encryption"></a>メッセージの暗号化

電子メールは、財務データ、法的契約、社外秘の製品情報、売上レポートや売上見込み、患者の医療情報、顧客や従業員の情報などの機密性の高い情報を交換するためによく使われています。その結果、メールボックスが機密性の高い大量の情報のリポジトリとして使用され、組織にとって情報漏洩が深刻な脅威となる可能性があります。

Office 365 Message Encryption を使用すると、組織は組織内外のユーザーとの間で暗号化されたメール メッセージを送受信できます。 Office 365 Message Encryption は、Outlook.com、Yahoo!、Gmail、およびその他のメール サービスで機能します。 メール メッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。

## <a name="how-office-365-message-encryption-works"></a>Office 365 Message Encryption の仕組み

この記事の以降の部分では、新しい OME 機能について説明します。

Office 365 Message Encryption は、Azure Information Protection の一部である Microsoft Azure Rights Management (Azure RMS) 上に構築されたオンライン サービスです。 このサービスには、電子メールのセキュリティ保護に役立つ暗号化、ID、承認ポリシーが含まれています。 メッセージを暗号化するには、アクセス許可管理のテンプレートである[転送不可オプション](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)および[暗号化のみ](/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)オプションを使用します。

ユーザーは、次のオプションを使用して、電子メール メッセージとさまざまな添付ファイルを暗号化できます。 サポートされているすべての添付ファイルの種類の一覧については、「[IRM ポリシーの対象となるメッセージ添付ファイルの種類](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)」を参照してください。

管理者は、この保護を適用するメール フロー ルールを定義することもできます。 たとえば、特定の受信者宛てのすべてのメッセージや件名行に特定の言葉が含まれるメッセージの暗号化を要求したり、受信者はメッセージのコンテンツのコピーや印刷の禁止を規定したりするルールを作成できます。

以前のバージョンの OME とは異なり、新しい機能は、組織内でメールを送信する場合でも、Microsoft 365 以外の受信者にメールを送信する場合でも、統一された送信者エクスペリエンスを提供します。 さらに、Outlook 2016 または Outlook on the web の Microsoft 365 アカウントに送信された保護された電子メール メッセージを受け取った受信者は、メッセージを表示するために他のアクションを実行する必要はありません。 シームレスに動作します。 また、他のメール クライアントやメール サービス プロバイダーを使用している受信者の操作性も向上しました。 詳細については、「[Office 365 の保護されたメッセージについて](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)」および「[保護されたメッセージを開く方法を教えてください](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)」を参照してください。

以前のバージョンの OME と新しい OME の間での機能の違いの詳細一覧は、「[OME のバージョンを比較する](ome-version-comparison.md)」をご覧ください。

暗号化メール フロー ルールに一致するメール メッセージを誰かが送信すると、メッセージは送信される前に暗号化されます。 Outlook Microsoft 365 クライアントを使用してメールを読み取るすべてのエンド ユーザーは、送信者と同じ組織にいなくても、暗号化された権限で保護されたメールのネイティブのファースト クラスの読み取りエクスペリエンスを受信します。 サポートされている Outlook クライアントには、Outlook デスクトップ、Outlook Mac、iOS および Android の Outlook Mobile、Outlook on the web (旧称: Outlook Web App) が含まれます。

Outlook.com、Gmail、および Yahoo アカウントに送られた暗号化され権限で保護されたメッセージを受信する暗号化されたメッセージの受信者には、Microsoft アカウント、Gmail、または Yahoo の資格情報を使用してすばやく認証を行える OME ポータルにユーザーをリダイレクトするラッパー メールが送信されます。

Outlook 以外のクライアントで暗号化または権利で保護されたメールを読み取るエンド ユーザーは、OME ポータルを使用して、受信した暗号化された権限で保護されたメッセージを表示します。

保護されたメールの送信者が GCC High で、受信者が GCC High の外部 (商用ユーザー、Outlook.com ユーザー、Gmail などの他のメール プロバイダーのユーザーを含む) の場合、受信者はラッパー メールを受信します。 ラッパー メッセージは、メッセージの閲覧と返信が行える OME ポータルにリダイレクトします。 上記以外の場合で、送信者と受信者の両方が GCC High の内部にいる場合は、たとえ受信者が同じ組織に存在していない場合でも、Outlook クライアントを使用してメールを読む受信者には暗号化され権限で保護されたメールでネイティブの、ファーストクラスの読み取り操作が提供されます。 GCC High での操作方法の違いの詳細については、「[OME のバージョンを比較する](ome-version-comparison.md)」を参照してください。

OME を使用して暗号化できるメッセージおよび添付ファイルのサイズ制限の詳細については、 「[Exchange Online の制限](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits)」を参照してください。

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Office 365 Advanced Message Encryption が OME 上で動作する仕組み

Office 365 Advanced Message Encryption を使用すると、複数のブランド テンプレートを作成することができます。これにより、受信者のメールの制御を細かく調整し、さまざまな組織構造をサポートするためのカスタム ブランド エクスペリエンスを作成できます。

暗号化された電子メールMicrosoft 365外部受信者のアクセスを柔軟に制御する必要があるコンプライアンスの義務を満たすのに役立ちます。 Office 365 の高度なメッセージ暗号化を使用すると、管理者として、機密情報の種類 (PII、財務、正常性の ID など) やキーワードを検出する自動ポリシーを使用して組織外で共有される機密メールを制御し、セキュリティで保護された Web ポータルから暗号化された電子メールへのアクセスを期限切れにすることで保護を強化できます。 管理者は、いつでも電子メールへのアクセスを取りMicrosoft 365 Web ポータルを介してアクセスされる暗号化された電子メールをさらに制御できます。

メッセージの失効と有効期限は、ユーザーが組織外の受信者に送信するメールでのみ機能します。 また、受信者は Web ポータル経由でメールにアクセスする必要があります。 受信者がメールを受信するのにポータルを使用するよう、ラッパーを適用するカスタム ブランド テンプレートを設定します。 次に、メール フロー ルールでブランド テンプレートを適用します。 Advanced Message Encryption の詳細については、「[Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)」を参照してください。

## <a name="defining-rules-for-office-365-message-encryption"></a>Office 365 Message Encryption のルールの定義

Office 365 Message Encryption の新機能を有効にする方法の 1 つとして、Exchange Online および Exchange Online Protection の管理者がメール フロー ルールを定義することができます。 これらのルールにより、メール メッセージの暗号化が求められる条件が規定されます。 暗号化アクションをルールで設定すると、そのルールの条件を満たすすべてのメッセージが送信前に暗号化されます。

メール フロー ルールは柔軟であるため条件を組み合わせることができ、1 つのルールで特定のセキュリティ要件を満たすことができます。 たとえば、指定したキーワードを含み、外部の受信者に宛てられたすべてのメッセージを暗号化するルールを作成できます。 Office 365 Message Encryption の新しい機能では、暗号化されたメールの受信者からの返信も暗号化します。

メール フロー ルールを作成して新しい OME 機能を活用する方法の詳細については、「[Office 365 でメール メッセージを暗号化するためにルールを定義する](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。

## <a name="get-started-with-the-new-ome-capabilities"></a>新しい OME 機能の使用を開始する

組織内で OME 新機能を使用する準備ができた場合は、「[新しい Office 365 Message Encryption 機能を設定する](set-up-new-message-encryption-capabilities.md)」をご覧ください。

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>暗号化されたメール メッセージの送信、表示、および返信

Office 365 Message Encryption では、Outlook と Outlook on the web から暗号化されたメールを送信できます。 さらに、管理者は、キーワードの一致や他の条件に基Microsoft 365メールを自動的に暗号化するメール フロー ルールを設定できます。

組織の暗号化されたメッセージの受信者は、Outlook for PC、Outlook for Mac、Outlook on the web、Outlook for iOS、Android 用 Outlook など、任意のバージョン Outlook でそれらのメッセージをシームレスに読み取る事が可能です。 他のメール クライアントで暗号化されたメッセージを受信するユーザーは、OME ポータルでメッセージを表示できます。

暗号化されたメッセージを送信および表示する方法の詳細なガイダンスについては、次の記事を参照してください。

|関連記事|記事の対象となるユーザーの種類|
|:-----|:-----|
|[Office 365 の保護されたメッセージについて](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|暗号化されたメッセージの仕組みや利用できるオプションについて詳しく知りたいエンド ユーザー。|
|[保護されたメッセージを開く方法を教えてください](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|自分宛てに送信された保護されたメッセージを読みたいエンド ユーザー。 この記事には、gmail や Yahoo など、Outlook 以外のアカウントを含む複数のバージョンのメール アカウントからメッセージを読み取Microsoft 365情報が含まれています。 。|
|[Outlook での暗号化されたメッセージの送信、表示、および返信](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)|暗号化されたメッセージの送信、表示、返信を Outlook で行うエンド ユーザー。 組織のメンバーではない場合でも、組織で送信された暗号化されたメッセージの通知を受け取Outlook。 Office 365 から送信された暗号化メッセージを表示して返信する方法については、こちらの記事を参照してください。|
|[デジタル署名または暗号化されたメッセージを送信する](https://support.microsoft.com/office/send-a-digitally-signed-or-encrypted-message-a18ecf7f-a7ac-4edd-b02e-687b05eff547)|暗号化されたメッセージの送信、表示、または返信を Outlook for Mac で行うエンド ユーザー。 この記事では、OME 以外の暗号化方法 (S/MIME など) の使用についても説明します。|
|[暗号化されたメッセージを Android デバイスで表示する](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|Office 365 Message Encryption で暗号化されたメッセージを Android デバイスで受信したエンド ユーザーは、無料の OME Viewer アプリを使用してメッセージを表示し、暗号化された返信を送信できます。 この記事では、その方法について説明します。|
|[iPhone または iPad で暗号化されたメッセージを表示する](https://support.microsoft.com/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)|Office 365 Message Encryption で暗号化されたメッセージを iPhone または iPad で受信したエンド ユーザーは、無料の OME Viewer アプリを使用してメッセージを表示し、暗号化された返信を送信できます。 この記事では、その方法について説明します。|
||