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
localization_priority: Normal
ms.date: 4/30/2019
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
description: この記事では、365 メッセージ暗号化の異なるバージョンOffice説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a587e27460d949811f9f30af0244cf325aaadac6
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741338"
---
# <a name="compare-versions-of-ome"></a>OME のバージョンを比較する

> [!IMPORTANT]
> 2021 年 2 月 28 日、Microsoft は Exchange Online での RMS ADサポートを廃止します。 Exchange メールボックスがオンラインで、オンプレミスの Active Directory RMS で IRM を使用しているハイブリッド環境を展開している場合は、Azure に移行する必要があります。 GCC 中程度の環境に展開した組織も影響を受ける。 詳細については、この記事AD「Exchange Online での RMS 非推奨の概要」を参照してください。

この記事の残りの部分では、従来の Office 365 Message Encryption (OME) と新しい OME 機能、および Office 365 Advanced Message Encryption を比較します。 新しい機能は、OME と Information Rights Management (IRM) の合併および新しいバージョンです。 GCC High に展開する固有の特性も概説します。 2 つのユーザーは組織内で共存できます。 新機能の動作方法については [、「365 message Encryption (OME) Officeを参照してください](ome.md)。

この記事は、365 Message Encryption に関する大規模なOfficeの一部です。 この記事は、管理者と ITPros を対象とします。 暗号化されたメッセージの送受信に関する情報を探している場合は [、Office 365 Message Encryption (OME)](ome.md) の記事の一覧を参照し、ニーズに最も適した記事を探します。

## <a name="overview-of-ad-rms-deprecation-in-exchange-online"></a>Exchange Online AD RMS 非推奨の概要

Exchange Online には、電子メール メッセージと添付ファイルのオンラインおよびオフライン保護を提供する Information Rights Management (IRM) 機能が含まれています。 既定では、Exchange Online は Azure Azure Information Protection を使用します。 ただし、組織は、オンプレミスの Active Directory Rights Management Service (RMS) を使用するように Exchange Online IRM を構成ADがあります。 ADの RMS サポートは終了しています。 代わりに、Azure Information Protection は RMS のAD置き換える必要があります。

開始する前に、組織の影響を確認して評価します。 組織が既に Azure Information Protection を使用して Exchange Online で電子メールを暗号化している場合は、何も行う必要があります。 Exchange メール フロー ルールを使用して電子メールを暗号化する場合 (たとえば、Office 365 Message Encryption を使用する場合)、セキュリティで保護された電子メールを変更する必要が生じしません。 それ以外の場合は、Azure Information Protection に切り替AD RMS の廃止に備える必要があります。

### <a name="prepare-for-ad-rms-deprecation"></a>RMS の非推奨AD準備する

Azure Information Protection を既にセットアップ済みで、使用していない場合は、Exchange Online PowerShell を使用してサービスを有効にしてください。 ローカル コンピューターで、組織内のグローバル管理者アクセス許可を持つ仕事または学校のアカウントを使用して、別のウィンドウで [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) にWindows PowerShellします。

Azure Information Protection を有効にするには、次のコマンドを入力Set-IrmConfigurationコマンドレットを使用します。

```powershell
Set-IrmConfiguration -AzureRMSLicensingEnabled $true
```

組織が Azure Information Protection をまだセットアップしていない場合は、RMS から Azure Information Protection に移行AD必要があります。 手順については、「RMS から Azure Information Protection への [移行AD」を参照してください](https://docs.microsoft.com/azure/information-protection/migrate-from-ad-rms-to-azure-rms)。

## <a name="side-by-side-comparison-of-features-and-capabilities"></a>機能と機能を並べて比較する

|           **状況**           | **レガシー OME**    | **RMS の IRM AD RM**        | **新しい OME 機能** |
|-----------------------------------|-------------------|-------------------|--------------------------|
|*暗号化されたメールの送信*        |Exchange メール フロー ルールを使用する|Outlook デスクトップまたは Outlook on the Web から開始されたエンド ユーザー。または Exchange メール フロー ルールを使用する|Outlook デスクトップ、Outlook for Mac、または Outlook on the Web から開始されたエンド ユーザー。Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) とデータ損失防止 (DLP) を使用して|
|*権限管理テンプレート*       |   該当なし      |[転送しない] オプションとカスタム テンプレート|[転送しない] オプション、暗号化専用オプション、およびカスタム テンプレート|
|*受信者の種類*                   |内部および外部の受信者|内部受信者のみ         |内部および外部の受信者|
|*内部受信者のエクスペリエンス*|受信者は HTML メッセージを受信し、Web ブラウザーまたはモバイル アプリでダウンロードして開きます。|Outlook クライアントでのネイティブ インライン エクスペリエンス|Outlook クライアントを使用する同じ組織内の受信者のネイティブ インライン エクスペリエンス。  受信者は、Outlook 以外のクライアントを使用して OME ポータルからメッセージを読み取ります (ダウンロードやアプリは必要ありません)。|
|*外部受信者のエクスペリエンス*|受信者は HTML メッセージを受信し、Web ブラウザーまたはモバイル アプリでダウンロードして開きます。|該当なし|Microsoft 365 受信者のネイティブ インライン エクスペリエンス。 他のすべての受信者は、OME ポータルからメッセージを読み取ります (ダウンロードやアプリは必要ありません)。|
|*添付ファイルのアクセス許可*           |添付ファイルの制限なし|添付ファイルが保護されている|添付ファイルは、[転送しない] オプションとカスタム テンプレートで保護されます。 管理者は、暗号化専用オプションの添付ファイルを保護するかどうかを選択できます。|
|*独自のキー (BYOK) のサポートを提供する*|なし                |なし               |BYOK がサポートされています          |
||

## <a name="advantages-of-the-new-ome-capabilities-over-legacy-ome"></a>従来の OME に対する新しい OME 機能の利点

新しい機能には、次の利点があります。

- 暗号化専用オプション (安全な共同作業を可能にする)、転送しないオプション、およびカスタム制限を使用する機能。
- 送信者は、Outlook Desktop、Outlook for Mac、Outlook on the Web クライアントから、新しい機能で暗号化されたメールを手動で送信できます。
- Microsoft 365 受信者は、サポートされている Outlook クライアントでインライン エクスペリエンスを使用できます。 または、管理者は、Microsoft 365 受信者にブランド化されたエクスペリエンスを表示できます。
- Gmail、Yahoo、Microsoft アカウントなど、Microsoft 365 以外のアカウントは、これらの受信者に優れたユーザー エクスペリエンスを提供する OME ポータルとフェデレーションされます。 他のすべての ID は、暗号化されたメッセージにアクセスするために 1 回きりパス コードを使用します。
- 管理者は、ブランド化をカスタマイズし、複数のブランド 化テンプレートを作成できます。
- 管理者は、新しい機能で暗号化されたメールを取り消す可能性があります。
- 新しい機能は、セキュリティ コンプライアンス センターを通じて詳細な使用状況レポートを &amp; 提供します。

## <a name="office-365-advanced-message-encryption-capabilities"></a>Office 365 高度なメッセージ暗号化機能

Office 365 Advanced Message Encryption は、新しい OME 機能の上に追加の機能を提供します。 Advanced Message Encryption 機能を使用するにはOffice 365 Message Encryption の新しい機能が組織にセットアップされている必要があります。 また、これらの機能を使用するには、受信者が OME ポータルを通じてメールをセキュリティで保護するために表示および返信する必要があります。 高度な機能は次のとおりです。

- メッセージの失効

- メッセージの有効期限

- 複数のブランド 化テンプレート

Office 365 Advanced Message Encryption は GCC High ではサポートされていません。

高度なメッセージ暗号化の使用の詳細については [、「Office 365 Advanced Message Encryption 」を参照してください](ome-advanced-message-encryption.md)。

## <a name="unique-characteristics-of-office-365-message-encryption-in-a-gcc-high-deployment"></a>GCC High 展開Office 365 メッセージ暗号化の固有の特性

GCC High 環境で Office 365 Message Encryption を使用する場合、受信者エクスペリエンスに関していくつかの固有の特性があります。

### <a name="encrypted-email-between-gcc-high-and-gcc-high-recipients"></a>GCC High と GCC High 受信者の間の暗号化された電子メール

送信者は、Outlook for PC および Mac および Outlook on the web の電子メールを手動で暗号化したり、Exchange メール フロー ルールを使用して電子メールを暗号化するポリシーを組織で設定できます。

GCC High 内の受信者は、他のすべてのユーザーと同じインライン読み取りエクスペリエンスを Outlook for PC および Mac および Outlook on the web で受け取る。

### <a name="encrypted-email-between-gcc-high-and-non-gcc-high-recipients"></a>GCC High 受信者と非 GCC 高受信者間の暗号化された電子メール

GCC High 内の送信者は、GCC High 境界の外部で暗号化された電子メールを送信でき、その逆も可能です。

GCC High 以外のすべての受信者 (商用 Microsoft 365 ユーザー、Outlook.com ユーザー、Gmail や Yahoo などの他のメール プロバイダーの他のユーザーを含む) は、ラッパー メールを受信します。 このラッパー メールは受信者を OME ポータルにリダイレクトし、受信者はメッセージの読み取りおよび返信を行います。 これは、GCC High 外部の送信者が GCC High に OME 暗号化メールを送信する場合にも当てはまる。

## <a name="coexistence-of-legacy-ome-and-the-new-capabilities-in-the-same-tenant"></a>従来の OME と同じテナントの新機能の共存

従来の OME と新しい機能の両方を同じテナントで使用できます。 管理者は、メール フロー ルールの作成時に使用する OME のバージョンを選択してこれを行います。

- 従来のバージョンの OME を指定するには、[Exchange メール フロー ルール] アクション [以前のバージョンの OME を適用する] **を使用します**。

- 新しい機能を指定するには、[Exchange メール フロー ルール] アクション **[365** メッセージOffice保護を適用する] を使用します。

ユーザーは、Outlook Desktop、Outlook for Mac、および Outlook on the web から新しい機能で暗号化されたメールを手動で送信できます。

## <a name="migrate-from-legacy-ome-to-the-new-capabilities"></a>従来の OME から新しい機能への移行

両方のバージョンの OME を共存させることができますが、ルール アクションを使用する古いメール フロー ルールを編集することを強くお勧めします。新しい機能を使用するには、以前のバージョンの **OME** を適用します。 これらのルールを更新して、[メール フロー ルール] アクション **[365 メッセージOffice保護を適用する] を使用します**。 手順については、「Define mail flow rules to encrypt email messages in Office [365」 を参照してください](define-mail-flow-rules-to-encrypt-email.md)。

## <a name="get-started-with-ome"></a>OME の使用を開始する

通常、新しい OME 機能は組織で自動的に有効になります。 組織内の新しい OME 機能の詳細については、「Set [up new Office 365 Message Encryption capabilitis](set-up-new-message-encryption-capabilities.md)」を参照してください。

Azure Information Protection を有効にしている場合、従来のバージョンの OME は組織で自動的に有効になります。 以前は、Azure Information Protection が有効になっていない場合でも、従来の OME が機能しました。 これはもはや当てはめではありません。

従来の OME の使用を開始するには、Azure Information Protection を有効にしている場合は、ルール アクション [以前のバージョンの OME を適用する] を使用するメール フロー ルール **を構成します**。 手順については、「メール メッセージを [暗号化するメール フロー ルールを定義する」を参照してください](define-mail-flow-rules-to-encrypt-email.md)。
