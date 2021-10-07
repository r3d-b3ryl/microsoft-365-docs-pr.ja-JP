---
title: メッセージ暗号化 (OME) バージョン比較
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
description: この記事では、さまざまなバージョンのバージョンの違いについて説明Office 365 Message Encryption。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 508a129cd472c8843e2af4a012560b17a44c49aa
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60194347"
---
# <a name="compare-versions-of-ome"></a>OME のバージョンを比較する

> [!IMPORTANT]
> 2021 年 2 月 28 日、Microsoft は、AD RMS のサポートをExchange Online。 Exchange メールボックスがオンラインで、オンプレミスの Active Directory RMS で IRM を使用しているハイブリッド環境を展開している場合は、Azure に移行する必要があります。 中程度の環境に展開GCC組織も影響を受ける。 詳細については、この記事AD「Exchange Online RMS の廃止の概要」を参照してください。

この記事の残りの部分では、従来Office 365 Message Encryption (OME) と新しい OME 機能と新しい OME 機能Office 365 Advanced Message Encryption。 新しい機能は、OME と Information Rights Management (IRM) の合併および新しいバージョンです。 また、High に展開する固有GCCの概要も示します。 2 つのユーザーは組織内で共存できます。 新しい機能の動作方法の詳細については、「Office 365 Message Encryption [(OME) 」を参照してください](ome.md)。

この記事は、この記事に関する一連の大きな記事Office 365 Message Encryption。 この記事は、管理者と ITPros を対象とします。 暗号化されたメッセージの送受信に関する情報を探しているだけの場合は[、Office 365 Message Encryption (OME)](ome.md)の記事の一覧を参照し、ニーズに最も適した記事を探します。

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>RMS のADの概要Exchange Online

Exchange Onlineには、電子メール メッセージと添付ファイルのオンラインおよびオフライン保護を提供する Information Rights Management (IRM) 機能が含まれています。 既定では、azure Exchange Online保護が使用されます。 ただし、組織は、オンプレミスの Active Directory Rights Management Service (EXCHANGE ONLINE RMS) を使用するように IRM を構成ADがあります。 ADの RMS サポートExchange Online終了しています。 代わりに、Azure Information Protection は RMS のAD置き換える必要があります。

この非推奨が組織に影響を与えるかどうかを評価するには、「AD RMS を Azure RMS に移行する方法」[をExchange Online。](/exchange/troubleshoot/administration/migrate-ad-rms-to-azure) この記事では、移行オプションに関する推奨事項について説明します。

## <a name="side-by-side-comparison-of-ome-features-and-capabilities"></a>OME 機能のサイド バイ サイド比較

|           **状況**           | **レガシー OME**    | **RMS の IRM AD RM**        | **新しい OME 機能** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*暗号化されたメールの送信*        |メール Exchangeルールを使用する|デスクトップまたは Web 上OutlookからOutlookエンド ユーザー。またはメール フロー Exchangeを介して|Web 上のデスクトップ、Outlook、Outlook for Mac、Outlookから開始されたエンド ユーザー。メール Exchangeルール (トランスポート ルールとも呼ばれる) とデータ損失防止 (DLP) を使用して|
|*権限管理テンプレート*       |   該当なし      |[転送しない] オプションとカスタム テンプレート|[転送しない] オプション、暗号化専用オプション、およびカスタム テンプレート|
|*受信者の種類*                   |内部および外部の受信者|内部受信者のみ         |内部および外部の受信者|
|*内部受信者のエクスペリエンス*|受信者は HTML メッセージを受信し、Web ブラウザーまたはモバイル アプリでダウンロードして開きます。|ネイティブ インライン エクスペリエンス (Outlook クライアント)|クライアントを使用して同じ組織内の受信者に対するネイティブ インライン エクスペリエンスOutlookします。  受信者は、ユーザー以外のクライアントを使用して OME ポータルからメッセージを読み取Outlook (ダウンロードやアプリは必要ありません)。|
|*外部受信者のエクスペリエンス*|受信者は HTML メッセージを受信し、Web ブラウザーまたはモバイル アプリでダウンロードして開きます。|該当なし|受信者のネイティブ インライン エクスペリエンスMicrosoft 365します。 他のすべての受信者は、OME ポータルからメッセージを読み取ります (ダウンロードやアプリは必要ありません)。|
|*添付ファイルのアクセス許可*           |添付ファイルの制限なし|添付ファイルが保護されている|添付ファイルは、[転送しない] オプションとカスタム テンプレートで保護されます。 管理者は、暗号化専用オプションの添付ファイルを保護するかどうかを選択できます。|
|*独自のキー (BYOK) のサポートを提供する*|なし                |なし               |BYOK がサポートされています          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>従来の OME に対する新しい OME 機能の利点

新しい機能には、次の利点があります。

- 暗号化専用オプション (安全な共同作業を可能にする)、転送しないオプション、およびカスタム制限を使用する機能。
- 送信者は、新しい機能で暗号化されたメールをデスクトップ、デスクトップ、Outlook、Outlook for MacクライアントOutlook on the webできます。
- Microsoft 365は、サポートされているクライアントでインライン エクスペリエンスを使用Outlookします。 または、管理者は、ブランド化されたエクスペリエンスをMicrosoft 365受信者に表示する方法を選択できます。
- Gmail、Yahoo、Microsoft アカウントMicrosoft 365外部のアカウントは、これらの受信者に優れたユーザー エクスペリエンスを提供する OME ポータルとフェデレーションされます。 他のすべての ID は、暗号化されたメッセージにアクセスするために 1 回きりパス コードを使用します。
- 管理者は、ブランド化をカスタマイズし、複数のブランド 化テンプレートを作成できます。
- 管理者は、新しい機能で暗号化されたメールを取り消す可能性があります。
- 新しい機能は、セキュリティ コンプライアンス センターを通じて詳細な使用状況レポートを &amp; 提供します。

## <a name="office-365-advanced-message-encryption-capabilities"></a>Office 365 Advanced Message Encryption機能

Office 365 Advanced Message Encryption、新しい OME 機能の上に追加の機能を提供します。 高度なメッセージ暗号化機能をOffice 365 Message Encryption、組織で新しい機能を設定する必要があります。 また、これらの機能を使用するには、受信者が OME ポータルを通じてメールをセキュリティで保護するために表示および返信する必要があります。 高度な機能は次のとおりです。

- メッセージの失効

- メッセージの有効期限

- 複数のブランド 化テンプレート

Office 365 Advanced Message Encryption High ではサポートGCCされません。

高度なメッセージ暗号化の使用の詳細については、「Office 365 Advanced Message Encryption」[を参照してください](ome-advanced-message-encryption.md)。

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>高い展開でのOffice 365 Message EncryptionのGCC特性

高レベル環境でOffice 365 Message EncryptionをGCC場合、受信者エクスペリエンスに関していくつかの固有の特性があります。

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>高い受信者と高GCC高GCC間の暗号化された電子メール

送信者は、pc および Mac および Outlook on the web の Outlook で電子メールを手動で暗号化するか、組織が Exchange メール フロー ルールを使用して電子メールを暗号化するポリシーを設定できます。

GCC High 内の受信者は、PC および Mac と他のすべてのユーザーと同Outlook読み取りOutlook on the webインライン読み取りエクスペリエンスを受け取る。

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>高受信者と非GCC受信者の間GCC電子メール

[高] GCC内の送信者は、暗号化された電子メールを高境界の外側GCC送信できます。その逆も同様です。

GCC High 以外のすべての受信者 (商用 Microsoft 365 ユーザー、Outlook.com ユーザー、Gmail や Yahoo などの他のメール プロバイダーの他のユーザーを含む) は、ラッパー メールを受信します。 このラッパー メールは受信者を OME ポータルにリダイレクトし、受信者はメッセージの読み取りおよび返信を行います。 これは、OME 暗号化メールを High に送信GCC外部の送信者にも当GCCです。

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>従来の OME と同じテナントの新機能の共存

従来の OME と新しい機能の両方を同じテナントで使用できます。 管理者は、メール フロー ルールの作成時に使用する OME のバージョンを選択してこれを行います。

- 従来のバージョンの OME を指定するには、[メール フロー ルールExchange以前のバージョンの OME を適用する] を **使用します**。

- 新しい機能を指定するには、[メール フロールールの適用] Exchangeと権限保護 **を適用するOffice 365 Message Encryptionを使用します**。

ユーザーは、デスクトップ、およびサーバーから新しい機能でOutlookメールを手動Outlook for Mac送信Outlook on the web。

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>従来の OME から新しい機能への移行

両方のバージョンの OME を共存させることができますが、ルール アクションを使用する古いメール フロー ルールを編集することを強くお勧めします。新しい機能を使用するには、以前のバージョンの **OME** を適用します。 これらのルールを更新して、[メール フロー ルールの適用] アクションを使用し **、Office 365 Message Encryption保護を適用します**。 手順については、「メール フロー ルールを定義してメール メッセージを暗号化する」[を参照Office 365。](define-mail-flow-rules-to-encrypt-email.md)

## <a name="get-started-with-ome"></a>OME の使用を開始する

通常、新しい OME 機能は組織で自動的に有効になります。 組織内の新しい OME 機能の詳細については、「新しい OME 機能をセットアップする[」をOffice 365 Message Encryptionしてください](set-up-new-message-encryption-capabilities.md)。

Azure Information Protection を有効にしている場合、従来のバージョンの OME は組織で自動的に有効になります。 以前は、Azure Information Protection が有効になっていない場合でも、従来の OME が機能しました。 これはもはや当てはめではありません。

従来の OME の使用を開始するには、Azure Information Protection を有効にしている場合は、ルール アクション [以前のバージョンの OME を適用する] を使用するメール フロー ルール **を構成します**。 手順については、「メール メッセージを [暗号化するメール フロー ルールを定義する」を参照してください](define-mail-flow-rules-to-encrypt-email.md)。
