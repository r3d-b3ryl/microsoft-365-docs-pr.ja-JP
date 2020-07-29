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
description: 組織の内外のユーザー間で暗号化された電子メールメッセージを送受信する方法について説明します。
ms.openlocfilehash: 542b540bb06998c1b90ef74485a4096ebc9ee0dc
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/28/2020
ms.locfileid: "45429933"
---
# <a name="message-encryption"></a>メッセージの暗号化

電子メールは、財務データ、法的契約、社外秘の製品情報、売上レポートや売上見込み、患者の医療情報、顧客や従業員の情報などの機密性の高い情報を交換するためによく使われています。その結果、メールボックスが機密性の高い大量の情報のリポジトリとして使用され、組織にとって情報漏洩が深刻な脅威となる可能性があります。

Office 365 Message Encryption を使用すると、組織は組織内外のユーザーとの間で暗号化されたメール メッセージを送受信できます。 Office 365 Message Encryption は、Outlook.com、Yahoo!、Gmail、およびその他のメール サービスで機能します。 メール メッセージの暗号化を使用すると、意図した受信者のみがメッセージの内容を表示できるようになります。

## <a name="how-office-365-message-encryption-works"></a>Office 365 Message Encryption の仕組み

この記事の以降の部分では、新しい OME 機能について説明します。

Office 365 Message Encryption は、Azure Information Protection の一部である Microsoft Azure Rights Management (Azure RMS) 上に構築されたオンライン サービスです。 このサービスには、メールをセキュリティで保護するための暗号化、ID、および認証ポリシーが含まれています。 メッセージを暗号化するには、アクセス許可管理のテンプレートである[転送不可オプション](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)および[暗号化のみ](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#encrypt-only-option-for-emails)オプションを使用します。

ユーザーは、次のオプションを使用して、電子メールメッセージとさまざまな添付ファイルを暗号化できます。 サポートされているすべての添付ファイルの種類の一覧については、「[IRM ポリシーの対象となるメッセージ添付ファイルの種類](https://support.office.com/article/bb643d33-4a3f-4ac7-9770-fd50d95f58dc#FileTypesforIRM)」を参照してください。

管理者は、この保護を適用するメール フロー ルールを定義することもできます。 たとえば、特定の受信者宛てのすべてのメッセージや件名行に特定の言葉が含まれるメッセージの暗号化を要求したり、受信者はメッセージのコンテンツのコピーや印刷の禁止を規定したりするルールを作成できます。

以前のバージョンの OME とは異なり、新機能により、組織内でメールを送信している場合も、Microsoft 365 の外部の受信者にも送信している場合でも、統合された送信者の環境が提供されます。 また、Outlook 2016 または web 上の Outlook で Microsoft 365 アカウントに送信される保護された電子メールメッセージを受信する受信者は、メッセージを表示するために追加のアクションを実行する必要はありません。 シームレスに動作します。 また、他のメール クライアントやメール サービス プロバイダーを使用している受信者の操作性も向上しました。 詳細については、「[Office 365 の保護されたメッセージについて](https://support.office.com/article/Learn-about-protected-messages-in-Office-365-2baf3ac7-12db-40a4-8af7-1852204b4b67)」および「[保護されたメッセージを開く方法を教えてください](https://support.office.com/article/How-do-I-open-a-protected-message-1157a286-8ecc-4b1e-ac43-2a608fbf3098)」を参照してください。

以前のバージョンの OME と新しい OME の間での機能の違いの詳細一覧は、「[OME のバージョンを比較する](ome-version-comparison.md)」をご覧ください。

暗号化メール フロー ルールに一致するメール メッセージを誰かが送信すると、メッセージは送信される前に暗号化されます。 Outlook クライアントを使用してメールを読むことができるすべての Microsoft 365 エンドユーザーは、送信者と同じ組織にいない場合でも、暗号化されていて、権利で保護されたメールのネイティブなファーストクラスの読み取りエクスペリエンスを受信します。 サポートされている Outlook クライアントには、Outlook デスクトップ、Outlook Mac、iOS および Android の Outlook Mobile、Outlook on the web (旧称: Outlook Web App) が含まれます。

Outlook.com、Gmail、および Yahoo アカウントに送られた暗号化され権限で保護されたメッセージを受信する暗号化されたメッセージの受信者には、Microsoft アカウント、Gmail、または Yahoo の資格情報を使用してすばやく認証を行える OME ポータルにユーザーをリダイレクトするラッパー メールが送信されます。

暗号化された、または権限で保護されたメールを Outlook 以外のクライアントで閲覧するエンドユーザーも、OME ポータルを使用して、受信した暗号化された、または権利で保護されたメッセージを表示します。

保護されたメールの送信者が GCC High の場合、受信者は、商用ユーザー、Outlook.com ユーザー、および Gmail などの他の電子メールプロバイダーのユーザーを含め、GCC の範囲外にある場合、受信者はラッパーメールを受信します。 ラッパー メッセージは、メッセージの閲覧と返信が行える OME ポータルにリダイレクトします。 上記以外の場合で、送信者と受信者の両方が GCC High の内部にいる場合は、たとえ受信者が同じ組織に存在していない場合でも、Outlook クライアントを使用してメールを読む受信者には暗号化され権限で保護されたメールでネイティブの、ファーストクラスの読み取り操作が提供されます。 GCC High での操作方法の違いの詳細については、「[OME のバージョンを比較する](ome-version-comparison.md)」を参照してください。

OME を使用して暗号化できるメッセージおよび添付ファイルのサイズ制限の詳細については、 「[Exchange Online の制限](https://technet.microsoft.com/library/exchange-online-limits.aspx)」を参照してください。

## <a name="how-office-365-advanced-message-encryption-works-on-top-of-ome"></a>Office 365 Advanced Message Encryption が OME 上で動作する仕組み

Office 365 Advanced Message Encryption を使用すると、複数のブランド テンプレートを作成することができます。これにより、受信者のメールの制御を細かく調整し、さまざまな組織構造をサポートするためのカスタム ブランド エクスペリエンスを作成できます。

Microsoft 365 の高度なメッセージ暗号化は、暗号化されたメールへの外部の受信者のアクセスをより柔軟に制御する必要があるコンプライアンスの義務を満たすのに役立つ情報を示します。 Office 365 の高度なメッセージ暗号化を使用すると、管理者は、機密情報の種類 (PII、金融、健康 Id など) やキーワードを検出する自動ポリシーを使用して、組織外で共有される機密メールを制御し、セキュリティで保護された web ポータルから暗号化電子メールへのアクセスを有効にして保護を強化できます。 管理者として、電子メールへのアクセスをいつでも取り消すことにより、Microsoft 365 web ポータルを通じてアクセスする暗号化メールをさらに制御することができます。

メッセージの失効と有効期限は、ユーザーが組織外の受信者に送信する電子メールに対してのみ機能します。 また、受信者は Web ポータル経由でメールにアクセスする必要があります。 受信者がメールを受信するのにポータルを使用するよう、ラッパーを適用するカスタム ブランド テンプレートを設定します。 次に、メール フロー ルールでブランド テンプレートを適用します。 Advanced Message Encryption の詳細については、「[Office 365 Advanced Message Encryption](ome-advanced-message-encryption.md)」を参照してください。

## <a name="defining-rules-for-office-365-message-encryption"></a>Office 365 Message Encryption のルールの定義

Office 365 Message Encryption の新機能を有効にする方法の 1 つとして、Exchange Online および Exchange Online Protection の管理者がメール フロー ルールを定義することができます。 これらのルールにより、メール メッセージの暗号化が求められる条件が規定されます。 暗号化アクションをルールで設定すると、そのルールの条件を満たすすべてのメッセージが送信前に暗号化されます。

メール フロー ルールは柔軟であるため条件を組み合わせることができ、1 つのルールで特定のセキュリティ要件を満たすことができます。 たとえば、指定したキーワードを含み、外部の受信者に宛てられたすべてのメッセージを暗号化するルールを作成できます。 Office 365 Message Encryption の新しい機能では、暗号化されたメールの受信者からの返信も暗号化します。

メール フロー ルールを作成して新しい OME 機能を活用する方法の詳細については、「[Office 365 でメール メッセージを暗号化するためにルールを定義する](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。

## <a name="get-started-with-the-new-ome-capabilities"></a>新しい OME 機能の使用を開始する

組織内で OME 新機能を使用する準備ができた場合は、「[新しい Office 365 Message Encryption 機能を設定する](set-up-new-message-encryption-capabilities.md)」をご覧ください。

## <a name="sending-viewing-and-replying-to-encrypted-email-messages"></a>暗号化されたメール メッセージの送信、表示、および返信

Office 365 Message Encryption では、Outlook と Outlook on the web から暗号化されたメールを送信できます。 また、管理者は、Microsoft 365 でメールフロールールを設定して、キーワード一致またはその他の条件に基づいてメールを自動的に暗号化することができます。

組織内の暗号化されたメッセージの受信者は、outlook for PC、outlook for Mac、outlook on the web、outlook for iOS、outlook for Android などの任意のバージョンの Outlook で、これらのメッセージをシームレスに読み取ることができます。 他のメール クライアントで暗号化されたメッセージを受信するユーザーは、OME ポータルでメッセージを表示できます。

暗号化されたメッセージを送信および表示する方法について詳しくは、次の記事を参照してください。

|||
|:-----|:-----|
|関連記事|記事の対象となるユーザーの種類|
|[Office 365 の保護されたメッセージについて](https://support.office.com/article/2baf3ac7-12db-40a4-8af7-1852204b4b67.aspx)|暗号化されたメッセージの仕組みや利用できるオプションについて詳しく知りたいエンド ユーザー。|
|[保護されたメッセージを開く方法を教えてください](https://support.office.com/article/1157a286-8ecc-4b1e-ac43-2a608fbf3098.aspx)|自分宛てに送信された保護されたメッセージを読みたいエンド ユーザー。 この記事には、複数のバージョンの Outlook および異なるメールアカウントからのメッセージの読み取りに関する情報が含まれています。これには、gmail や Yahoo! などの Microsoft 365 の外部のアカウントを含みます。 。|
|[Outlook での暗号化されたメッセージの送信、表示、および返信](https://support.microsoft.com/office/send-view-and-reply-to-encrypted-messages-in-outlook-for-pc-eaa43495-9bbb-4fca-922a-df90dee51980)|暗号化されたメッセージの送信、表示、返信を Outlook で行うエンド ユーザー。 組織のメンバーでない場合でも、Outlook で送信された暗号化されたメッセージの通知を受信します。 Office 365 から送信された暗号化メッセージを表示して返信する方法については、こちらの記事を参照してください。|
|[デジタル署名または暗号化されたメッセージを送信する](https://support.microsoft.com/office/send-a-digitally-signed-or-encrypted-message-a18ecf7f-a7ac-4edd-b02e-687b05eff547)|暗号化されたメッセージの送信、表示、または返信を Outlook for Mac で行うエンド ユーザー。 この記事では、OME 以外の暗号化方法 (S/MIME など) の使用についても説明します。|
|[暗号化されたメッセージを Android デバイスで表示する](https://support.office.com/article/83d60f17-2305-407a-a762-7d518401fdeb)|Office 365 Message Encryption で暗号化されたメッセージを Android デバイスで受信したエンド ユーザーは、無料の OME Viewer アプリを使用してメッセージを表示し、暗号化された返信を送信できます。 この記事では、その方法について説明します。|
|[iPhone または iPad で暗号化されたメッセージを表示する](https://support.microsoft.com/office/view-protected-messages-on-your-iphone-or-ipad-4d631321-0d26-4bcc-a483-d294dd0b1caf)|Office 365 Message Encryption で暗号化されたメッセージを iPhone または iPad で受信したエンド ユーザーは、無料の OME Viewer アプリを使用してメッセージを表示し、暗号化された返信を送信できます。 この記事では、その方法について説明します。|
||
