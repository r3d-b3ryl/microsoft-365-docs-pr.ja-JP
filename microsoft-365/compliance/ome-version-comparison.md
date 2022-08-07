---
title: メッセージ暗号化バージョンの比較
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: この記事では、さまざまなバージョンのメッセージ暗号化の違いについて説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 44eb59a160af9ecbe171e1c9b63f67e6ac608fe0
ms.sourcegitcommit: cd9df1a681265905eef99c039f7036b2fa6e8b6d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67276265"
---
# <a name="compare-versions-of-message-encryption"></a>メッセージの暗号化のバージョンを比較する

> [!IMPORTANT]
> 2021 年 2 月 28 日、Microsoft はExchange Onlineでの AD RMS のサポートを非推奨にしました。 Exchange メールボックスがオンラインで、オンプレミスの Active Directory RMS で IRM を使用しているハイブリッド環境をデプロイした場合は、Azure に移行する必要があります。 GCC 中等度環境にデプロイした組織も影響を受ける。 詳細については、この記事の「Exchange Onlineでの AD RMS の非推奨の概要」を参照してください。

この記事の残りの部分では、従来のOffice 365メッセージ暗号化 (OME) をMicrosoft Purview Message Encryptionおよび Microsoft Purview Advanced Message Encryption と比較します。 Microsoft Purview Message Encryptionは、OME と Information Rights Management (IRM) の両方の合併および新しいバージョンです。 GCC High へのデプロイの固有の特性についても説明します。 2 つを組織内に共存させることができます。 新機能のしくみの詳細については、「[Office 365 メッセージ暗号化 (OME)](ome.md)」を参照してください。

この記事は、メッセージの暗号化に関する大規模な一連の記事の一部です。 この記事は、管理者と ITPros を対象としています。 暗号化されたメッセージの送受信に関する情報だけを探している場合は、メッセージ暗号化の記事の一覧を [参照し、](ome.md) ニーズに最も適した記事を見つけます。

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Exchange Onlineでの AD RMS の非推奨の概要

Exchange Onlineには、電子メール メッセージと添付ファイルをオンラインおよびオフラインで保護する Information Rights Management (IRM) 機能が含まれています。 既定では、Exchange Onlineは Azure Information Protectionを使用します。 ただし、組織は、オンプレミスの Active Directory Rights Management Service (AD RMS) を使用するように IRM Exchange Online構成している可能性があります。 Exchange Onlineでの AD RMS のサポートは廃止されます。 代わりに、Azure Information Protectionは AD RMS を完全に置き換えます。

この非推奨が組織に影響を与えるかどうかを評価するには、「[Exchange Onlineで AD RMS を Azure RMS に移行する方法](/exchange/troubleshoot/administration/migrate-ad-rms-to-azure)」を参照してください。 この記事では、移行オプションに関する推奨事項について説明します。

## <a name="side-by-side-comparison-of-message-encryption-features-and-capabilities"></a>メッセージ暗号化の機能と機能を並べて比較する

|           **状況**           | **レガシー OME**    | **AD RMS の IRM**        | **Microsoft Purview のメッセージの暗号化** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*暗号化されたメールを送信する*        |Exchange メール フロー ルールを使用する|Outlook デスクトップまたは Outlook on the Web から開始されたエンド ユーザー。または Exchange メール フロー ルールを使用して|Outlook デスクトップ、Outlook for Mac、または Outlook on the Web から開始されたエンド ユーザー。Exchange メール フロー ルール (トランスポート ルールとも呼ばれます) とデータ損失防止 (DLP) を通じて開始されます。|
|*Rights Management テンプレート*       |   該当なし      |[転送不可] オプションとカスタム テンプレート|転送しないオプション、暗号化専用オプション、およびカスタム テンプレート|
|*受信者の種類*                   |内部および外部受信者|内部受信者のみ         |内部および外部受信者|
|*内部受信者のエクスペリエンス*|受信者は HTML メッセージを受け取り、Web ブラウザーまたはモバイル アプリでダウンロードして開きます。|Outlook クライアントでのネイティブ インライン エクスペリエンス|Outlook クライアントを使用して、同じ組織内の受信者のネイティブ インライン エクスペリエンス。  受信者は、Outlook 以外のクライアントを使用して OME ポータルからメッセージを読み取ることができます (ダウンロードやアプリは必要ありません)。|
|*外部受信者のエクスペリエンス*|受信者は HTML メッセージを受け取り、Web ブラウザーまたはモバイル アプリでダウンロードして開きます。|該当なし|Microsoft 365 受信者向けのネイティブ インライン エクスペリエンス。 他のすべての受信者は、OME ポータルからメッセージを読み取ることができます (ダウンロードやアプリは必要ありません)。|
|*添付ファイルのアクセス許可*           |添付ファイルに制限なし|添付ファイルが保護されている|添付ファイルは、[転送不可] オプションとカスタム テンプレートで保護されます。 管理者は、暗号化専用オプションの添付ファイルを保護するかどうかを選択できます。|
|*独自のキー (BYOK) サポートを持ち込む*|なし                |なし               |BYOK がサポートされています          |
||

## <a name="advantages-of-microsoft-purview-message-encryption-over-legacy-ome"></a>従来の OME よりもMicrosoft Purview Message Encryptionの利点

新しい機能には、次の利点があります。

- 暗号化専用オプション (セキュリティで保護されたコラボレーションを可能にする)、転送しないオプション、およびカスタム制限を使用する機能。
- 送信者は、Outlook Desktop、Outlook for Mac、Outlook on the web クライアントから、新しい機能で暗号化されたメールを手動で送信できます。
- Microsoft 365 の受信者は、サポートされている Outlook クライアントでインライン エクスペリエンスを使用できるようになります。 または、管理者は、Microsoft 365 受信者にブランド化されたエクスペリエンスを表示することもできます。
- Gmail、Yahoo、Microsoft アカウントなど、Microsoft 365 の外部のアカウントは、OME ポータルとフェデレーションされ、受信者のユーザー エクスペリエンスが向上します。 他のすべての ID では、1 回限りのパス コードを使用して、暗号化されたメッセージにアクセスします。
- 管理者は、ブランドをカスタマイズし、複数のブランド テンプレートを作成できます。
- 管理者は、新しい機能で暗号化されたメールを取り消すことができます。
- 新しい機能は、セキュリティ &amp; コンプライアンス センターを通じて詳細な使用状況レポートを提供します。

## <a name="microsoft-purview-advanced-message-encryption-capabilities"></a>Microsoft Purview Advanced Message Encryption 機能

Microsoft Purview Advanced Message Encryption には、Microsoft Purview Message Encryptionに加えて追加機能が用意されています。 高度なメッセージ暗号化を使用するには、組織内でMicrosoft Purview Message Encryptionを設定する必要があります。 また、これらの機能を使用するには、受信者はMicrosoft Purview Message Encryption ポータルを使用してセキュリティで保護されたメールを表示して返信する必要があります。 高度な機能は次のとおりです。

- メッセージ失効

- メッセージの有効期限

- 複数のブランド化テンプレート

高度なメッセージ暗号化は GCC High ではサポートされていません。

高度なメッセージ暗号化の使用については、「 [Microsoft Purview Advanced Message Encryption](ome-advanced-message-encryption.md)」を参照してください。

## <a name="unique-characteristics-of-microsoft-purview-message-encryption-in-a-gcc-high-deployment"></a>GCC High デプロイにおけるMicrosoft Purview Message Encryptionの固有の特性

GCC High 環境でMicrosoft Purview Message Encryptionを使用する予定の場合は、受信者エクスペリエンスに固有の特性がいくつかあります。

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>GCC High 受信者と GCC High 受信者の間の暗号化された電子メール

送信者は Outlook for PC と Mac とOutlook on the webでメールを手動で暗号化できます。または、組織は Exchange メール フロー ルールを使用して電子メールを暗号化するポリシーを設定できます。

GCC High 内の受信者は、Outlook for PC と Mac でインライン読み取りエクスペリエンスを受け取り、他のすべてのユーザーと同じOutlook on the webを受け取ります。

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>GCC High 受信者と GCC 以外の受信者間の暗号化された電子メール

GCC High 内の送信者は、GCC High 境界の外部で暗号化された電子メールを送信でき、その逆も可能です。

GCC High 以外のすべての受信者 (商用 Microsoft 365 ユーザー、Outlook.com ユーザー、Gmail や Yahoo などの他のメール プロバイダーの他のユーザーを含む) は、ラッパー メールを受け取ります。 このラッパー メールは、受信者をMicrosoft Purview Message Encryption ポータルにリダイレクトします。受信者はメッセージの読み取りと返信を行うことができます。 これは、GCC High 以外の送信者が GCC High に OME 暗号化されたメールを送信する場合にも当てはまります。

## <a name="coexistence-of-legacy-ome-and-microsoft-purview-message-encryption-in-the-same-tenant"></a>同じテナント内のレガシ OME とMicrosoft Purview Message Encryptionの共存

レガシ OME とMicrosoft Purview Message Encryptionの両方を同じテナントで使用できます。 管理者は、メール フロー ルールを作成するときに使用するメッセージ暗号化のバージョンを選択することで、これを行います。

- 従来のバージョンの OME を指定するには、Exchange メール フロー ルールアクション **OME の以前のバージョンを適用する** を使用します。

- Microsoft Purview Message Encryptionを指定するには、Exchange メール フロー ルールアクション [メッセージの **暗号化と権限の保護Office 365適用** する] を使用します。

ユーザーは、Outlook Desktop、Outlook for Mac、およびOutlook on the webからMicrosoft Purview Message Encryptionで暗号化されたメールを手動で送信できます。

## <a name="migrate-from-legacy-ome-to-microsoft-purview-message-encryption"></a>レガシ OME からMicrosoft Purview Message Encryptionに移行する

両方のバージョンを共存させることができますが、ルール アクション **OME の以前のバージョンを適用** してMicrosoft Purview Message Encryptionを使用する古いメール フロー ルールを編集することを非常に推奨します。 これらのルールを更新して、メール フロー ルールアクション **[メッセージの暗号化と権限の保護Office 365適用** する] を使用するように更新し、RMS テンプレートの一覧で [暗号化] を選択します。 手順については、「 [メール メッセージを暗号化するためのメール フロー ルールを定義する](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。

## <a name="get-started-with-ome"></a>OME の使用を開始する

通常、Microsoft Purview Message Encryptionは組織に対して自動的に有効になります。 組織内のMicrosoft Purview Message Encryptionの詳細については、「[Microsoft Purview Message Encryptionの設定](set-up-new-message-encryption-capabilities.md)」を参照してください。

Azure Information Protectionを有効にした場合、組織のレガシ バージョンの OME が自動的に有効になります。 以前は、Azure Information Protectionが有効になっていない場合でも、レガシ OME は機能しました。 これはもうそうではありません。

レガシ OME の使用を開始するには、Azure Information Protectionを有効にしている場合は、ルール アクション **OME の以前のバージョンを適用** するを使用するメール フロー ルールを構成します。 手順については、「 [メール メッセージを暗号化するためのメール フロー ルールを定義する](define-mail-flow-rules-to-encrypt-email.md)」を参照してください。
