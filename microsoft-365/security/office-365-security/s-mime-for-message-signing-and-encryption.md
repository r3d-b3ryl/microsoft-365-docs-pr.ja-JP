---
title: S/MIME で暗号化を行う Exchange Online - Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 887c710b-0ec6-4ff0-8065-5f05f74afef3
description: 管理者は、Exchange Online で S/MIME (Secure/Multipurpose Internet Mail Extensions) を使用して電子メールを暗号化し、デジタル署名する方法について学習できます。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d189bf7f52dd6f9fb11dc360c17d5fe15729c9fa
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205686"
---
# <a name="smime-for-message-signing-and-encryption-in-exchange-online"></a>メッセージ署名と暗号化の S/MIME Exchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


S/MIME (Secure/Multipurpose Internet Mail Extensions) は、デジタル署名されたメッセージと暗号化されたメッセージを送信するための広く受け入れられているメソッド (より正確にはプロトコル) です。 S/MIME では電子メールを暗号化し、デジタル署名を行うことができます。 電子メール メッセージで S/MIME を使用すると、そのメッセージを受信する人は、受信トレイにあるものが送信者によって作成されたメッセージそのものであることがわかります。 また、メッセージを受信する人は、そのメッセージが確かに特定の送信者から送信されたものであり、その送信者になりすました別の誰かからのものでないこともわかります。 このために、S/MIME には認証、メッセージの整合性、発信元の否認防止 (デジタル署名を使用) などの暗号化セキュリティ サービスが用意されています。 また、これは電子メッセージングのプライバシーとデータ セキュリティ (暗号化を使用) の強化にも役立ちます。 電子メール関連での S/MIME の歴史とアーキテクチャに関する詳細な背景情報については、「[S/MIME について](/previous-versions/tn-archive/aa995740(v=exchg.65))」を参照してください。

管理者Exchange Online、組織内のメールボックスに対して S/MIME ベースのセキュリティを有効にできます。 S/MIME を設定するには、PowerShell と共にExchange Onlineリンクされているトピックのガイダンスを使用します。 サポートされている電子メール クライアントで S/MIME を使用するには、組織内のユーザーが署名と暗号化の目的で発行された証明書と、オンプレミスの Active Directory ドメイン サービス (AD DS) に発行されたデータを持っている必要があります。 ユーザー AD DS は、インターネット上のリモート施設やクラウドベースのサービスではなく、ユーザーが制御する物理的な場所にあるコンピューター上に置く必要があります。 DS の詳細についてはAD Active Directory [ドメイン サービスの概要を参照してください](/windows-server/identity/ad-ds/get-started/virtual-dc/active-directory-domain-services-overview)。

## <a name="supported-scenarios-and-technical-considerations"></a>サポートされるシナリオと技術的な考慮事項

次の任意のエンドポイントで機能するように S/MIME をセットアップできます。

- Outlook 2010 以降
- Web 上の Outlook (旧称 Outlook Web App)
- Exchange ActiveSync (EAS)

これらの各エンド ポイントで S/MIME を設定する手順は少し異なります。 通常、次の手順を実行する必要があります。

1. セキュリティ ベースWindows証明機関 (CA) をインストールし、S/MIME 証明書を発行する公開キー インフラストラクチャをセットアップします。 サードパーティの証明書プロバイダーによって発行された証明書もサポートされています。 詳細については、「[Active Directory 証明書サービスの概要](/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831740(v=ws.11))」を参照してください。

   **注**:

   - サード パーティ CA によって発行された証明書は、すべてのクライアントとデバイスによって自動的に信頼されるという利点があります。 内部のプライベート CA によって発行された証明書は、クライアントやデバイスによって自動的に信頼されるのではなく、すべてのデバイス (電話など) がプライベート証明書を信頼するように構成できる場合ではありません。

   - ルート証明書の代わりに中間証明書を使用して、ユーザーに証明書を発行する方法を検討してください。 そうすることで、証明書を取り消して再発行する必要がある場合、ルート証明書はそのまま残ります。

2. **UserSMIMECertificate** 属性または **UserCertificate** 属性AD DS アカウントにユーザー証明書を発行します。

3. 組織Exchange Online、適切なバージョンの Azure AD を使用して、AD DS から Azure Active Directory にユーザー証明書を同期AD Connect。 次に、これらの証明書は Azure Active Directory から Exchange Online のディレクトリに同期され、受信者へのメッセージの暗号化に使用されます。

4. S/MIME を検証するためには、仮想の証明書のコレクションを設定します。この情報は、電子メールの署名を検証する際に Web 上の Outlook により使用され、そのメールが信頼される証明書により署名されたことが確認されます。

5. S/MIME を使用する Outlook エンド ポイントまたは EAS エンド ポイントを設定します。

> [!NOTE]
> Mac、iOS、Android、その他の非デバイスOutlook Web 上で S/MIME コントロールをインストールWindowsできません。 詳細については、「Web で[S/MIME を使用してメッセージを暗号化Outlookを参照してください](https://support.microsoft.com/office/878c79fc-7088-4b39-966f-14512658f480)。

## <a name="set-up-smime-with-outlook-on-the-web"></a>Web 上の Outlook での S/MIME のセットアップ

Web 上のユーザーと一緒Exchange Online S/MIME をOutlookには、次の重要な手順が含まれます。

1. [Outlook on the web の S/MIME 設定を構成する](configure-s-mime-settings-for-outlook-web-app.md)
2. [S/MIME を検証するための仮想証明書コレクションを設定する](set-up-virtual-certificate-collection-to-validate-s-mime.md)
3. [S/MIME 用にユーザー証明書を Office 365 に同期させる](sync-user-certificates-to-office-365-for-s-mime.md)

## <a name="related-message-encryption-technologies"></a>関連するメッセージ暗号化テクノロジ

メッセージ のセキュリティが重要になると、管理者はセキュリティで保護されたメッセージングの原則と概念を理解する必要があります。 この理解は、利用可能な保護関連テクノロジ (S/MIME を含む) の種類が増えているため、特に重要です。 S/MIME と電子メールのコンテキストでの動作の詳細については [、「S/MIME について」を参照してください](/previous-versions/tn-archive/aa995740(v=exchg.65))。 さまざまな暗号化テクノロジが連携して、保管されているメッセージと転送中のメッセージの保護を提供します。 S/MIME は次のようなテクノロジと同時に機能しますが、それらに依存してはいません。

- **トランスポート層セキュリティ (TLS)** は、盗聴防止に役立てるために電子メール サーバー間のトンネルまたはルートを暗号化します。

- **Secure Sockets Layer (SSL) は**、電子メール クライアントとサーバー間の接続Microsoft 365します。

- **BitLocker** データ センターのハード ドライブ上のデータを暗号化して、誰かが不正アクセスを取得した場合、データを読み取る事ができない。

### <a name="smime-compared-with-office-365-message-encryption"></a>S/MIME と Office 365 のメッセージ暗号化との比較

S/MIME には B2B (企業間取引) および B2C (企業-消費者間取引) の状況でよく使用される証明書および公開のインフラストラクチャが必要です。 ユーザーは、S/MIME で暗号化キーを制御し、送信する各メッセージにキーを使用するかどうかを選択できます。 Outlook などの電子メール プログラムはデジタル署名と署名の検証を実行するために、信頼できるルート証明機関の場所を検索します。 Office 365 のメッセージの暗号化は、組織内外の任意の受信者に送信されるメールを暗号化するための、管理者が構成できる (個々のユーザーは構成できない) ポリシー ベースの暗号化サービスです。 これは、Azure Rights Management (RMS) 上に構築され、公開キー インフラストラクチャに依存しないオンライン サービスです。 Office 365 Message Encryption、組織のブランドを使用してメールをカスタマイズする機能など、追加の機能も提供します。 暗号化の詳細については、「Office 365 Message Encryption暗号化[」を参照Office 365。](../../compliance/encryption.md)

## <a name="more-information"></a>詳細情報

[Outlook on the web](/exchange/exchange-admin-center)

[Secure Mail (2000)](/previous-versions/windows/it-pro/windows-2000-server/cc962043(v=technet.10))