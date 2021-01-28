---
title: Message Encryption (OME) のバージョン比較
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: この記事では、365 Message Encryption の異なるバージョン間Office説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 30344a9cbe8629804f5026fc809577923965b7bc
ms.sourcegitcommit: b3bb5bf5efa197ef8b16a33401b0b4f5663d3aa0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/28/2021
ms.locfileid: "50032624"
---
# <a name="compare-versions-of-ome"></a>OME のバージョンを比較する

> [!IMPORTANT]
> 2021 年 2 月 28 日に、Microsoft は Exchange Online の AD RMS のサポートを廃止します。 Exchange メールボックスがオンラインのハイブリッド環境を展開し、オンプレミスの Active Directory RMS で IRM を使用している場合は、Azure に移行する必要があります。 GCC Moderate 環境に展開した組織も影響を受ける。 詳細については、このAD記事の「Exchange Online での RMS の廃止の概要」を参照してください。

この記事の残りの部分では、従来の Office 365 Message Encryption (OME) と新しい OME 機能、および Office 365 Advanced Message Encryption を比較します。 新しい機能は、OME と Information Rights Management (IRM) の両方の合併および新しいバージョンです。 GCC High に展開する独自の特性も示します。 2 つのユーザーは組織で共存できます。 新しい機能の動作方法については、「OME Office [365 Message Encryption (OME)」を参照してください](ome.md)。

この記事は、Office 365 Message Encryption に関する大規模な一連の記事の一部です。 この記事は、管理者と ITPros を対象にしています。 暗号化されたメッセージの送受信に関する情報を探しているだけの場合は [、Office 365 Message Encryption (OME)](ome.md) の記事の一覧を参照し、ニーズに最も適した記事を探してください。

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Exchange Online AD RMS 非推奨の概要

Exchange Online には、電子メール メッセージと添付ファイルをオンラインおよびオフラインで保護する Information Rights Management (IRM) 機能が含まれています。 既定では、Exchange Online は Azure Azure Information Protection を使用します。 ただし、組織は、オンプレミスの Active Directory Rights Management サービス (AD RMS) を使用するように Exchange Online IRM を構成している可能性があります。 ADの RMS サポートは廃止されます。 代わりに、Azure Information Protection は RMS AD置き換える必要があります。

始める前に、組織への影響を確認して評価します。 組織で既に Azure Information Protection を使用して Exchange Online の電子メールを暗号化している場合は、何もする必要があります。 たとえば Office 365 Message Encryption を使用する場合など、Exchange メール フロー ルールを使用してメールを暗号化する場合は、セキュリティで保護された電子メールを変更する必要が生じしません。 それ以外の場合は、Azure Information Protection に切り替AD RMS の廃止に備える必要があります。

### <a name="prepare-for-ad-rms-deprecation"></a>RMS の廃止AD準備する

Azure Information Protection を既にセットアップ済みで、まだ使用していない場合は、Exchange Online PowerShell を使用してサービスを有効にしてください。 ローカル コンピューターで、組織のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、次のウィンドウで [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) Windows PowerShellします。

Azure Information Protection を有効にするには、次のコマンドをSet-IrmConfigurationコマンドレットを使用します。

```powershell
Set-IrmConfiguration -AzureRMSLicensingEnabled $true
```

組織で Azure Information Protection をまだセットアップしていない場合は、組織の RMS から Azure Information Protection ADする必要があります。 手順については、「AD RMS から Azure Information Protection への移行」を [参照してください](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms)。

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>機能の並べて比較

|           **状況**           | **レガシー OME**    | **AD RMS の IRM**        | **新しい OME 機能** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*暗号化されたメールの送信*        |Exchange メール フロー ルールを使用する|Outlook デスクトップまたは Web 上の Outlook から開始されたエンドユーザーまたは Exchange メール フロー ルールを使用する|Outlook デスクトップ、Outlook for Mac、または Web 上の Outlook から開始されたエンドユーザーExchange メール フロー ルール (トランスポート ルールとも呼ばれる) およびデータ損失防止 (DLP) を介して|
|*権限管理テンプレート*       |   N/A      |[転送しない] オプションとカスタム テンプレート|[転送しない] オプション、Encrypt-Onlyテンプレート|
|*受信者の種類*                   |内部および外部の受信者|内部受信者のみ         |内部および外部の受信者|
|*内部受信者のエクスペリエンス*|受信者は HTML メッセージを受け取り、Web ブラウザーまたはモバイル アプリでダウンロードして開きます|Outlook クライアントでのネイティブ インライン エクスペリエンス|Outlook クライアントを使用する同じ組織内の受信者のネイティブ インライン エクスペリエンス。  受信者は、Outlook 以外のクライアントを使用して OME ポータルからメッセージを読み取ります (ダウンロードやアプリは必要ありません)。|
|*外部受信者のエクスペリエンス*|受信者は HTML メッセージを受け取り、Web ブラウザーまたはモバイル アプリでダウンロードして開きます|N/A|Microsoft 365 受信者向けネイティブ インライン エクスペリエンス。 他のすべての受信者は、OME ポータルからメッセージを読み取ります (ダウンロードやアプリは必要ありません)。|
|*添付ファイルのアクセス許可*           |添付ファイルに制限なし|添付ファイルが保護されている|添付ファイルは、[転送しない] オプションとカスタム テンプレートで保護されます。 管理者は、添付ファイルを保護するかどうかをEncrypt-Onlyオプションを選択できます。|
|*独自のキー (BYOK) のサポートを提供する*|なし                |なし               |BYOK のサポート          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>従来の OME と新しい OME 機能の利点

新しい機能には、次の利点があります。

- セキュリティで保護されたEncrypt-Only、転送しない、カスタム制限を有効にする)、ユーザー設定の制限を使用する機能。
- 送信者は、Outlook デスクトップ、Outlook for Mac、および Web 上の Outlook クライアントから、新しい機能を使用して暗号化されたメールを手動で送信できます。
- Microsoft 365 の受信者は、サポートされている Outlook クライアントでインライン エクスペリエンスを使用できます。 または、管理者は、Microsoft 365 の受信者にブランド化されたエクスペリエンスを表示することができます。
- Gmail、Yahoo、Microsoft アカウントなど、Microsoft 365 以外のアカウントは OME ポータルとフェデレーションされ、これらの受信者のユーザー エクスペリエンスが向上します。 他のすべての ID は、暗号化されたメッセージにアクセスするためにワンタイム パス コードを使用します。
- 管理者は、ブランド化をカスタマイズし、複数のブランド 化テンプレートを作成できます。
- 管理者は、新しい機能を使用して暗号化されたメールを取り消す可能性があります。
- 新しい機能は、セキュリティ コンプライアンス センターを通じて詳細な利用状況レポートを &amp; 提供します。

## <a name="office-365-advanced-message-encryption-capabilities"></a>Office 365 Advanced Message Encryption の機能

Office 365 Advanced Message Encryption は、新しい OME 機能の上に追加の機能を提供します。 Advanced Message Encryption 機能を使用するには、Office 365 Message Encryption の新しい機能が組織でセットアップされている必要があります。 また、これらの機能を使用するには、受信者は OME ポータルを通じてセキュリティで保護されたメールを表示して返信する必要があります。 高度な機能は次のとおりです。

- メッセージの取り消し

- メッセージの有効期限

- 複数のブランド 化テンプレート

Office 365 Advanced Message Encryption は GCC High ではサポートされていません。

Advanced Message Encryption の使用の詳細については、「Office [365 Advanced Message Encryption」を参照してください](ome-advanced-message-encryption.md)。

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>GCC High 展開Office 365 Message Encryption の固有の特性

GCC High 環境で Office 365 Message Encryption を使用する予定の場合、受信者のエクスペリエンスに関していくつかの固有の特性があります。

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>GCC High 受信者と GCC High 受信者間の暗号化された電子メール

送信者は、OUTLOOK for PC、Mac、Outlook on the web で電子メールを手動で暗号化するか、Exchange メール フロー ルールを使用してメールを暗号化するポリシーを設定できます。

GCC High 内の受信者は、PC および Mac 用の Outlook および Web 上の Outlook で、他のすべてのユーザーと同じインライン読み取りエクスペリエンスを受け取っています。

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>GCC High 受信者と非 GCC High 受信者間の暗号化された電子メール

GCC High 内の送信者は、GCC High 境界の外部で暗号化された電子メールを送信できます。その逆も可能です。

商用の Microsoft 365 ユーザー、Outlook.com ユーザー、Gmail や Yahoo などの他のメール プロバイダーの他のユーザーを含む、GCC High 外のすべての受信者は、ラッパー メールを受信します。 このラッパー メールは、受信者をメッセージの読み取りおよび返信が可能な OME ポータルにリダイレクトします。 これは、GCC High 外部の送信者が OME 暗号化メールを GCC High に送信する場合にも当てはまる。

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>従来の OME と同じテナント内の新機能の共存

従来の OME と新しい機能の両方を同じテナントで使用できます。 管理者は、メール フロー ルールを作成するときに使用する OME のバージョンを選択することで、これを行います。

- レガシ バージョンの OME を指定するには、Exchange メール フロー ルールアクションを使用して以前のバージョンの **OME を適用します**。

- 新しい機能を指定するには、Exchange メール フロー ルールアクションを使用して **、365 Message Encryption** とOffice保護を適用します。

ユーザーは、Outlook デスクトップ、Outlook for Mac、Outlook on the web の新機能で暗号化されたメールを手動で送信できます。

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>従来の OME から新しい機能への移行

OME の両方のバージョンが共存できる場合でも、ルールアクションを使用する古いメール フロー ルールを編集することを強くお勧めします。新しい機能を使用するには、以前のバージョンの **OME** を適用します。 これらのルールを更新して、メール フロー ルールのアクション Apply Office **365 Message Encryption および Rights Protection を使用します**。 手順については [、「365](define-mail-flow-rules-to-encrypt-email.md)で電子メール メッセージを暗号化するメール フロー ルールOffice参照してください。

## <a name="get-started-with-ome"></a>OME の使用を開始する

通常、新しい OME 機能は組織に対して自動的に有効になります。 組織内の新しい OME 機能の詳細については [、「Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md)」を参照してください。

Azure Information Protection を有効にしている場合、組織ではレガシ バージョンの OME が自動的に有効になります。 以前は、Azure Information Protection が有効になっていない場合でも、従来の OME は機能しました。 これはもう当てはめでなくなりました。

従来の OME の使用を開始するには、Azure Information Protection を有効にしている場合は、ルールアクションを使用するメール フロー ルールを構成します。以前のバージョンの **OME を適用します**。 手順については、「メール メッセージを [暗号化するメール フロー ルールの定義」を参照してください](define-mail-flow-rules-to-encrypt-email.md)。
