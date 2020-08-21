---
title: Exchange Online での暗号化用の S/MIME - Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: 管理者は、Exchange Online で S/MIME (Secure/Multipurpose Internet Mail Extensions) を使用してメールを暗号化し、デジタル署名を行う方法について学習できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ca865fa8ef658b4715d18e09fe9cbc1cffb201e6
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845922"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>Exchange Online でのメッセージの署名と暗号化の S/MIME

S/MIME (Secure/Multipurpose Internet Mail Extensions) は、デジタル署名され、暗号化されたメッセージを送信するための広く受け入れられた方式 (より正確にです。 S/MIME では電子メールを暗号化し、デジタル署名を行うことができます。 電子メール メッセージで S/MIME を使用すると、そのメッセージを受信する人は、受信トレイにあるものが送信者によって作成されたメッセージそのものであることがわかります。 また、メッセージを受信する人は、そのメッセージが確かに特定の送信者から送信されたものであり、その送信者になりすました別の誰かからのものでないこともわかります。 このために、S/MIME には認証、メッセージの整合性、発信元の否認防止 (デジタル署名を使用) などの暗号化セキュリティ サービスが用意されています。 また、これは電子メッセージングのプライバシーとデータ セキュリティ (暗号化を使用) の強化にも役立ちます。 電子メール関連での S/MIME の歴史とアーキテクチャに関する詳細な背景情報については、「[S/MIME について](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65))」を参照してください。

Exchange Online 管理者は、組織内のメールボックスに対して S/MIME ベースのセキュリティを有効にできます。 ここにリンクされているトピックのガイダンスと Exchange Online PowerShell を使用して S/MIME をセットアップします。 サポートされている電子メール クライアントで S/MIME を使用するには、組織内のユーザーが署名と暗号化を行うための証明書と、オンプレミスの Active Directory ドメイン サービス (AD DS) に発行されたデータが必要です。 これらの AD DS は、リモート機能やインターネット上のクラウドベースのサービスでは管理せず、ユーザーが管理する物理的な場所にあるコンピューター上に配置されている必要があります。 接続 DS の詳細については AD、「Active Directory ドメイン [サービスの概要」を参照してください](https://docs.microsoft.com/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)。

## <a name="supported-scenarios-and-technical-considerations"></a>サポートされるシナリオと技術的な考慮事項

次の任意のエンドポイントで機能するように S/MIME をセットアップできます。

- Outlook 2010 以降
- Web 上の Outlook (旧称 Outlook Web App)
- Exchange ActiveSync (EAS)

これらの各エンドポイントに S/MIME をセットアップする手順は、それぞれ少し異なります。 一般的には、次の手順を実行する必要があります。

1. Windows ベースの証明機関 (CA) をインストールし、S/MIME 証明書を発行するための公開キー基盤を設定します。 サードパーティの証明書プロバイダーによって発行された証明書もサポートされています。 詳細については、「[Active Directory 証明書サービスの概要](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11))」を参照してください。

   **注**:

   - サードパーティの CA によって発行された証明書には、すべてのクライアントとデバイスによって自動的に信頼される利点があります。 内部のプライベート CA によって発行された証明書は、クライアントとデバイスによって自動的に信頼されるものではないため、プライベート証明書を信頼するようにすべてのデバイス (電話など) が構成されるものではない。

   - ユーザーに証明書を発行するには、ルート証明書ではなく中間証明書を使用してください。 このようにすると、証明書を取り消して発行し直す必要があれば、ルート証明書はそのまま残ります。

2. **UserSMIMECertificate**または**UserCertificate、AD、** オンプレミスのアカウントでユーザー証明書を発行します。

3. Exchange Online 組織の場合は、適切なバージョンの Azure AD Connect を使用 ADして、仮想 DS のユーザー証明書を Azure AD Directory にADします。 次に、これらの証明書は Azure Active Directory から Exchange Online のディレクトリに同期され、受信者へのメッセージの暗号化に使用されます。

4. S/MIME を検証するためには、仮想の証明書のコレクションを設定します。この情報は、電子メールの署名を検証する際に Web 上の Outlook により使用され、そのメールが信頼される証明書により署名されたことが確認されます。

5. S/MIME を使用する Outlook エンド ポイントまたは EAS エンド ポイントを設定します。

> [!NOTE]
> Mac、iOS、Android、またはその他の Windows 以外のデバイスの Outlook on the web に S/MIME コントロールをインストールすることはできません。 詳細については [、「Outlook on the web で S/MIME を使用してメッセージを暗号化する」を参照してください](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480)。

## <a name="setup-smime-with-outlook-on-the-web"></a>Outlook on the web での S/MIME のセットアップ

Web 上の Outlook で Exchange Online 用に S/MIME をセットアップするには、次の主要な手順に従います。

1. [Outlook on the web の S/MIME 設定を構成する](configure-s-mime-settings-for-outlook-web-app.md)
2. [S/MIME を検証するための仮想証明書コレクションを設定する](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [S/MIME 用にユーザー証明書を Office 365 に同期させる](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>関連するメッセージ暗号化テクノロジ

メッセージのセキュリティがより重要になるにつも、管理者はセキュリティで保護されたメッセージングの原則と概念を理解する必要があります。 S/MIME を含むさまざまな保護関連テクノロジ (S/MIME を含む) を利用可能ながりが生じていないので、この理解は特に重要です。 S/MIME と電子メールでの S/MIME のしくみについて理解するには [、「S/MIME について」を参照してください](https://docs.microsoft.com/previous-versions/tn-archive/aa995740(v=exchg.65))。 さまざまな暗号化テクノロジが連携して、保管されているメッセージと転送中のメッセージの保護を提供します。 S/MIME は次のようなテクノロジと同時に機能しますが、それらに依存してはいません。

- **トランスポート層セキュリティ (TLS)** は、盗聴防止に役立てるために電子メール サーバー間のトンネルまたはルートを暗号化します。

- **Secure Sockets Layer (SSL)** は、電子メール クライアントと Microsoft 365 サーバー間の接続を暗号化します。

- **BitLocker** は、データセンターのハード ドライブ上のデータを暗号化するので、ユーザーが無許可でアクセスした場合に読み取れないようにします。

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME と Office 365 のメッセージ暗号化との比較

S/MIME には B2B (企業間取引) および B2C (企業-消費者間取引) の状況でよく使用される証明書および公開のインフラストラクチャが必要です。 ユーザーは、S/MIME で暗号化キーを制御し、送信する各メッセージにキーを使用するかどうかを選択できます。 Outlook などの電子メール プログラムはデジタル署名と署名の検証を実行するために、信頼できるルート証明機関の場所を検索します。 Office 365 のメッセージの暗号化は、組織内外の任意の受信者に送信されるメールを暗号化するための、管理者が構成できる (個々のユーザーは構成できない) ポリシー ベースの暗号化サービスです。 これは Azure Rights Management (RMS) 上に構築されたオンライン サービスで、公開キー基盤には含めません。 Office 365 Message Encryption には、組織のブランドでメールをカスタマイズする機能など、追加機能も用いられます。 Office 365 Message Encryption の詳細については、「記事 [365 での暗号化」Officeを参照してください](https://docs.microsoft.com/microsoft-365/compliance/encryption)。

## <a name="more-information"></a>詳細情報

[Outlook on the web](https://docs.microsoft.com/exchange/exchange-admin-center)

[セキュリティで保護されたメール (2000)](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))
