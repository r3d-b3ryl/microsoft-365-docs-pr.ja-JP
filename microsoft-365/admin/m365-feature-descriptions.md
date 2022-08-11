---
title: Microsoft 365 機能の説明
ms.author: office365servicedesc
author: pamelaar
manager: gailw
audience: ITPro
ms.topic: reference
f1_keywords:
- microsoft-365-and-office-365-general-information
ms.service: o365-administration
ms.localizationpriority: medium
ms.custom:
- Adm_ServiceDesc
- Adm_ServiceDesc_top
ms.assetid: 721676a0-5108-488e-ae0c-7316617d0006
description: Microsoft 365 機能の説明で使用できる情報について説明します。
ms.openlocfilehash: 40f0b9379b0a4105f1292d283de2785dc652591d
ms.sourcegitcommit: 414682b9bf42dc19a89c893d3c515aee9765b6e4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2022
ms.locfileid: "67281270"
---
# <a name="microsoft-365-feature-descriptions"></a>Microsoft 365 機能の説明

# <a name="user-account-management"></a>[**ユーザー アカウント管理**](#tab/User-account-management)

## <a name="user-account-management"></a>ユーザー アカウントの管理

Microsoft は、ユーザーを作成、管理、および認証する次の方法をサポートします。 ただし、このトピックには、個々の Microsoft リソースへのアクセスを許可または禁止するセキュリティ機能に関する情報は含まれません (たとえば、Microsoft Exchange Onlineでのロールベースのアクセス制御、Microsoft Office SharePoint Onlineでのセキュリティの構成など)。 これらの機能の詳細については、[**Exchange Onlineサービスの説明**](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)と [**SharePoint Online サービスの説明**](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-service-description)を参照してください。 管理タスクの実行に役立つツールの情報については、「[Microsoft アカウントを管理するためのツール](/office365/enterprise/manage-office-365-accounts)」を参照してください。 日常的な管理タスクを実行する方法については、「[一般的な管理タスク](/office365/admin/manage/manage)」を参照してください。
  
**サブスクリプションのサインイン、インストール、アンインストール、またはキャンセルに関するヘルプが必要ですか?** ヘルプを表示する: Office  | [Canceling Office 365](https://support.office.com/article/Cancel-Office-365-for-business-b1bc0bef-4608-4601-813a-cdd9f746709a)[の](https://support.office.com/article/where-to-sign-in-to-office-365-for-business-e9eb7d51-5430-4929-91ab-6157c5a050b4) | [インストールまたはアンインストール](https://support.office.com/article/download-and-install-or-reinstall-office-365-or-office-2019-on-a-pc-or-mac-4414eaaf-0478-48be-9c42-23adc4716658)にサインインする
  
その他の問題については、[Microsoft サポート センター](https://support.microsoft.com/contactus/)にアクセスしてください。 中国の 21Vianet が運用している Office 365 に対するサポートを受けるには、[21Vianet サポート チーム](https://support.office.com/article/Get-technical-billing-and-subscription-support-for-Office-365-operated-by-21Vianet-671FB12E-F5D8-4CDF-B3E9-E8068A9AA496)にお問い合わせください。
  
**サインイン オプション:** Microsoft には、 **職場または学校アカウント (クラウド ID) とフェデレーション アカウント (フェデレーション ID)** の 2 つのシステムをユーザー **ID に** 使用できます。 ID の種類は、ユーザー エクスペリエンスおよびユーザー アカウントの管理オプションに加えて、ハードウェアとソフトウェアの要件や、展開に関する他の検討事項にも影響します。

**職場または学校のアカウント (クラウド ID)** - ユーザーは、Microsoft クラウド サービスにサインインするために、他のデスクトップまたは企業のクレデンシャルとは別に、Azure ActiveDirectory クラウド資格情報を受け取ります。 これは既定の ID で、展開の複雑さを最小にするためにこの ID を使用することをお勧めします。 職場または学校のアカウント用のパスワードは、Azure Active Directory [ パスワード ポリシー ](/previous-versions/azure/jj943764(v=azure.100)) を使用します。

**フェデレーション アカウント (フェデレーション ID)** - シングル サインオン (SSO) を使用するオンプレミスの Active Directory を使用する組織のすべてのサブスクリプションについて、ユーザーは Active Directory の資格情報を使用して Microsoft サービスにサインインできます。 会社の Active Directory は、パスワード ポリシーを格納し制御します。 SSO の詳細については、「 [シングル サインオンのロードマップ](/previous-versions/azure/azure-services/hh967643(v=azure.100))」を参照してください。

**シングル サインオン:** シングル サインオンを使用する組織の場合、ドメイン上のすべてのユーザーが同じ ID システム (クラウド ID またはフェデレーション ID) を使用する必要があります。 たとえば、社内システムにアクセスしないため 1 つのクラウド ID のみを必要とするユーザー グループと、Microsoft および社内システムの両方を使用する別のユーザー グループが存在する場合があります。 Office 365 に **contractors.contoso.com** と **staff.contoso.com** などの 2 つのドメインを追加して、2 つのドメインのうち一方のみに SSO をセットアップします。 ドメイン全体は、クラウド ID からフェデレーション ID に、またはフェデレーション ID からクラウド ID に変換することができます。

**認証：** SharePoint Online で作成された匿名アクセスのインターネット サイトを除き、ユーザーは Microsoft サービスにアクセスするときに認証する必要があります。 **先進認証**、 **クラウド ID 認証**、 **フェデレーション ID 認証**。 Microsoft は形式ベースの認証を使用しており、ネットワークを網羅する認証トラフィックは、ポート 443 を使用して常に TLS/SSL で暗号化されます。 認証トラフィックは、Microsoft サービスの帯域幅のごくわずかな部分のみを使用します。

**先進認証** - 先進認証は、Microsoft 認証ライブラリ ベースのサインインをプラットフォーム間で Office クライアント アプリにもたらします。 これにより、多要素認証 (MFA) によるサインイン、SAML ベースのサードパーティ製 ID プロバイダーから Office クライアント アプリケーションへのサインイン、スマート カードや証明書をベースとする認証機能を使用したサインインなどが可能になります。 また、Microsoft Outlook を使用していなくても基本認証プロトコルを使用できるようになります。 Office アプリケーション全体での最新の認証の可用性などの詳細については、「[Office 2013 および Office 2016 のクライアント アプリの先進認証のしくみ](/office365/enterprise/modern-auth-for-office-2013-and-2016)」を参照してください。 Exchange Online では、先進認証が既定でオンになっています。 オンまたはオフにする方法については、「[Exchange Online で先進認証を有効にする](/exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)」を参照してください。

**クラウド ID 認証** - クラウド IDを 持つユーザーは、従来のチャレンジ/レスポンスを使用して認証されます。 Web ブラウザーは、Microsoft サインイン サービスにリダイレクトされます。ここで、職場または学校のアカウントのユーザー名とパスワードを入力します。 サインイン サービスは、ユーザーの資格情報を認証し、サービス トークンを生成します。Web ブラウザーは、このサービス トークンを要求されたサービスに表示して、ユーザーを登録します。

**フェデレーション ID 認証** - フェデレーション ID を持つユーザーは、Active Directory フェデレーション サービス (AD FS) 2.0 またはその他のセキュリティ トークン サービスを使用して認証されます。 Web ブラウザーは、Microsoft サインインサービスにリダイレクトされます。ここで、企業 ID をユーザー プリンシパル名 (UPN、例: _isabel@contoso.com_) の形式で入力します。 サインイン サービスは、フェデレーション ドメインの一部であることを決定し、認証のためにオンプレミスのフェデレーション サーバーにリダイレクトすることを提供します。 デスクトップ (参加しているドメイン) にログオンしている場合は、(Kerberos または NTLMv2 を使用して) 認証され、オンプレミスのセキュリティ トークン サービスによってログオン トークンが生成され、Web ブラウザーが Microsoft サインイン サービスに投稿します。 サインイン サービスは、ログオン トークンを使用して、サービス トークンを生成します。Web ブラウザーは、このサービス トークンを要求されたサービスに表示して、ユーザーを登録します。 利用可能なセキュリティ トークン サービスの一覧については、「[シングル サインオンのロードマップ](/previous-versions/azure/azure-services/hh967643(v=azure.100))」を参照してください。

**多要素認証:** Multi-Factor Authentication では、ユーザーがパスワードを正しく入力した後、スマートフォンで電話、テキスト メッセージ、またはアプリ通知を確認する必要があります。 Only after this second authentication can the user sign in. Microsoft 管理者は、Microsoft 365 管理センターで多要素認証にユーザーを登録できます。 [多要素認証](/office365/admin/security-and-compliance/set-up-multi-factor-authentication)に関する詳細情報。

**リッチ クライアント認証:** Microsoft Office デスクトップ アプリケーションなどのリッチ クライアントの場合、認証は、 **Microsoft Online Services Sign-In アシスタント** と **SSL 経由の基本/プロキシ認証** の 2 つの方法で行うことができます。 Microsoft サービスの適切な検出と認証を確実にするため、管理者は、リッチ クライアント（Microsoft Office 2010 など）を使用して Office 365 に接続する各ワーク ステーションに一連のコンポーネントと更新を適用する必要があります。 デスクトップ セットアップは、必要な更新プログラムでワークステーションを構成する自動化ツールです。 詳細については、「[現在の Office デスクトップを使用する](https://support.office.com/article/3324b8b8-dceb-45e2-ac24-c642720108f7)」をご覧ください。

**Microsoft Online Services サインイン アシスタント** - デスクトップ セットアップによってインストールされるサインイン アシスタントには、サインイン サービスからサービス トークンを取得してリッチ クライアントに返すクライアント サービスが含まれています。 クラウド ID を持っている場合、ユーザーは資格情報のプロンプトを受け取ります。クライアント サービスは、認証のために、このプロンプトを サインイン サービスに送信します (WS-Trust を使用)。 ユーザーがフェデレーション ID を所有している場合、クライアント サービスは、まず AD FS 2.0 サーバーに接続し、資格情報を認証して (Kerberos または NTLMv2 を使用) ログオン トークンを取得します。このログオン トークンは サインイン サービスに送信されます (WS-Federation および WS-Trust を使用)。

**SSL を介した基本/プロキシ認証** - Outlook クライアントは、SSL を介した基本認証ク資格情報を ExchangeOnline に渡します。 Exchange Online は、認証要求を ID プラットフォームにプロキシし、次にオンプレミスの Active Directory フェデレーションサーバー (SSO 用) にプロキシします。 

**サインイン エクスペリエンス:** サインイン エクスペリエンスは、使用中の ID の種類によって変わります。
  
| サービス | クラウド ID | フェデレーション ID |
|:-----|:-----|:-----|
| Outlook 2016 |セッションごとにサインイン <sup>1</sup> |セッションごとにサインイン <sup>2</sup> |
| Outlook 2013 |セッションごとにサインイン <sup>1</sup> |セッションごとにサインイン <sup>2</sup> |
| Windows 7 で Outlook 2010 または Office 2007 を使用 |セッションごとにサインイン <sup>1</sup> |セッションごとにサインイン <sup>2</sup> |
| Windows Vista で Outlook 2010 または Office Outlook 2007 を使用 |セッションごとにサインイン <sup>1</sup> |セッションごとにサインイン <sup>2</sup> |
| Microsoft Exchange ActiveSync |セッションごとにサインイン <sup>1</sup> |セッションごとにサインイン <sup>2</sup> |
| POP、IMAP、Outlook for Mac |セッションごとにサインイン <sup>1</sup> |セッションごとにサインイン <sup>2</sup> |
| Web エクスペリエンス: Microsoft 365 管理センター/Outlook on the web/SharePoint Online/Office for the web |ブラウザー セッションごとにサインイン <sup>4</sup> |セッションごとにサインイン <sup>3</sup> |
| SharePoint Online で Office 2010 または Office 2007 を使用 |SharePoint Online セッションごとにサインイン <sup>4</sup> |SharePoint Online セッションごとにサインイン <sup>3</sup> |
| Skype for Business Online |セッションごとにサインイン <sup>1</sup> |プロンプトなし |
| Outlook for Mac |セッションごとにサインイン <sup>1</sup> |セッションごとにサインイン <sup>2</sup> |

<sup>1</sup> 最初に要求された時点で、今後の使用を目的にパスワードを保存することができます。 パスワードを変更するまで、別のプロンプトは表示されません。 <br/> 
<sup>2</sup> 会社の資格情報を入力します。 パスワードを保存できます。パスワードが変更されるまで、もう一度入力を求めるメッセージは表示されません。 <br/> 
<sup>3</sup> すべてのアプリケーションは、ユーザー名を入力するか、クリックしてサインインすることを要求します。 コンピューターがドメインに参加している場合、パスワードの入力を求めるメッセージは表示されません。 [ **サインインしたままにする** ] を選択した場合、サインアウトするまで、もう一度メッセージは表示されません。 <br/> 
<sup>4</sup> [ **サインインしたままにする** ] を選択した場合、サインアウトするまで、もう一度メッセージは表示されません。

**ユーザー アカウントを作成する:** ユーザーを追加するには、複数の方法があります。 詳細については、「[ユーザーを個別または一括で追加する - 管理 ヘルプ](/office365/admin/add-users/add-users)と[ユーザーの追加、ライセンスの割り当て - Microsoft 365 管理者|Microsoft Docs](/microsoft-365/admin/add-users/add-users)。中国で 21Vianet によって運用されているOffice 365を使用している場合は、「[21Vianet が運営するOffice 365でユーザー アカウントを作成または編集する - 管理 ヘルプ」を](/office365/admin/add-users/add-users)参照してください。

**ユーザー アカウントを削除する:** アカウントを削除する方法は、ディレクトリ同期を使用しているかどうかによって異なります。 ディレクトリ同期を使用していない場合は、管理者ページを使用するか、Windows PowerShellを使用してアカウントを削除できます。 ディレクトリ同期を使用している場合は、Office 365からではなく、ローカル Active Directory からユーザーを削除する必要があります。

**削除されたアカウント:** アカウントが削除されると、アカウントは非アクティブになります。 削除後約 30 日間は、アカウントを復元することができます。 アカウントの削除と復元の詳細については、「[ユーザーの削除](/office365/admin/add-users/delete-a-user)と[ユーザーの復元](/office365/admin/add-users/restore-user)」を参照してください。または、中国で 21Vianet によって運用されているOffice 365を使用している場合は、「[21Vianet によって操作されるOffice 365でユーザー アカウントを作成または編集する - 管理 ヘルプ」を](/office365/admin/add-users/add-users)参照してください。

**パスワード管理:** パスワード管理のポリシーと手順は、ID システムによって異なります。

**クラウド ID パスワード管理:** クラウド ID を使用すると、アカウントの作成時にパスワードが自動的に生成されます。 クラウド ID パスワードの強度要件の詳細については、「[パスワード ポリシー](/previous-versions/azure/jj943764(v=azure.100))」を参照してください。 セキュリティを強化するため、最初に Microsoft サービスにアクセスする時点で、ユーザーはパスワードを変更する必要があります。 その結果、ユーザーは Microsoft サービスにアクセスする前に、Microsoft 365 管理センターにサインインし、パスワードの変更を求めるメッセージを表示する必要があります。 管理者は、パスワードの有効期限ポリシーを設定できます。 詳細については、「 [ユーザーのパスワードの有効期限ポリシーを設定する](/office365/admin/manage/set-password-expiration-policy)」を参照してください。

**クラウド ID のパスワード リセット:** クラウド ID を持つユーザーのパスワードをリセットするためのツールがいくつかあります。**管理パスワードのリセット、Outlook on the web****でのパスワードの変更**、**ロールベースのパスワードのリセット権限**、**Windows PowerShellを使用したパスワードのリセット**。

**管理者によるパスワードの再設定** - ユーザーがパスワードを紛失または忘れた場合、管理者は管理センターで、または Windows PowerShell を使用してユーザーのパスワードをリセットできます。 ユーザーは、自分の現在のパスワードを知っている場合に、自分のパスワードだけを変更できます。 Enterprise プランでは、管理者が自分のパスワードをなくすか忘れた場合、全体管理者の役割が割り当てられた別の管理者が Microsoft 365 管理センターで、または WindowsPowerShell を使用して、管理者のパスワードを再設定することができます。 詳細については、「[Office 365 の管理者パスワードを再設定する](/office365/admin/add-users/reset-passwords)」を参照してください。 中国で 21Vianet によって運用されているOffice 365で作業している場合は、「[21Vianet によって運用されているOffice 365でパスワードを変更またはリセット](https://support.office.com/article/change-or-reset-your-password-in-office-365-operated-by-21vianet-d8eb5b62-9d0e-4267-a9bf-2aa491ee6d0b)する」を参照してください。

**Outlook on the web を使用したユーザーによるパスワード変更** - Outlook on the web オプション ページには、ユーザーを **[パスワードの変更]** ページにリダイレクトする、パスワード変更のハイパーリンクが含まれています。 ユーザーは、以前のパスワードを知っている必要があります。 詳細については、「 [Outlook Web アプリでパスワードを変更する](https://support.office.com/article/change-password-in-outlook-web-app-50bb1309-6f53-4c24-8bfd-ed24ca9e872c)」を参照してください。 中国で 21Vianet によって運用されているOffice 365を使用している場合は、「[21Vianet が運用するOffice 365でパスワードを変更またはリセット](https://support.office.com/article/change-or-reset-your-password-in-office-365-operated-by-21vianet-d8eb5b62-9d0e-4267-a9bf-2aa491ee6d0b)する」を参照してください。

**パスワードを再設定する役割ベースの権限** - Enterprise プランでは、ヘルプデスクのスタッフなどの承認されたユーザーに、全サービスの管理者にすることなく、**[パスワードの再設定]** を実行するユーザー権限や、定義済みの役割やカスタムの役割を使用してパスワードを変更する権限を割り当てることができます。 既定では、Enterprise プランの場合、全体管理者、パスワード管理者、またはユーザー管理の管理者の役割が割り当てられた管理者がパスワードを変更できます。 詳細については、「[管理者ロールを割り当てる](/office365/admin/add-users/assign-admin-roles)」を参照してください。

**WindowsPowerShell を使用してパスワードを再設定する** - サービス管理者は、WindowsPowerShell を使用してパスワードを再設定することができます。

**フェデレーション ID パスワード管理:** フェデレーション ID を使用する場合、パスワードは Active Directory で管理されます。 オンプレミスのセキュリティ トークン サービスは、ユーザーのローカル Active Directory パスワードをインターネット経由で Office 365 に渡すことなく、Federation Gateway による認証をネゴシエートします。 ローカル パスワード ポリシーを使用するか、Web クライアントの場合には 2 要素認証を使用します。 パスワードの変更ハイパーリンクが含まれていないOutlook on the web。 ユーザーは、標準の社内ツールを使用して、またはデスクトップ PC のログオン オプションでパスワードを変更します。

**ディレクトリ同期:** 組織環境 [でシングル サインオン (SSO)](/previous-versions/azure/azure-services/dn441213(v=azure.100)) が有効になっているディレクトリ同期があり、フェデレーション ID プロバイダーに影響を与える障害が発生した場合、フェデレーション サインイン用のパスワード同期バックアップでは、ドメインをパスワード同期に手動で切り替えるオプションが提供されます。パスワード同期を使用すると、停止が修正されている間にユーザーがアクセスできるようになります。 パスワード同期を使用すると、ユーザーは停止の修復作業中でも Office 365 にアクセスできます。[シングル サインオンからパスワード同期に切り替える方法](https://go.microsoft.com/fwlink/p/?LinkId=509832)をご確認ください。

**ライセンス管理:** ライセンスを使用すると、ユーザーは一連の Microsoft サービスにアクセスできます。 管理者は、必要なサービスにアクセスするためのライセンスを各ユーザーに割り当てます。 たとえば、Skype for Business Online へのアクセス権は割り当て、SharePoint Online へのアクセス権は割り当てないということができます。

**請求：** Microsoft 課金管理者は、ユーザー ライセンスの数や会社が使用する追加サービスの数など、サブスクリプションの詳細を変更できます。 「[ライセンスの割り当てまたは解除](/office365/admin/subscriptions-and-billing/assign-licenses-to-users)」を確認してください。 21Vianet によって運用されているOffice 365を使用している場合は、「[21Vianet によって運用Office 365ライセンスの割り当てまたは削除](/office365/admin/subscriptions-and-billing/assign-licenses-to-users)」を参照してください。

**グループ管理:** SharePoint Online では、サイトへのアクセスを制御するためにセキュリティ グループが使用されます。 セキュリティ グループは、Microsoft 365 管理センターで作成できます。 セキュリティ グループの詳細については、「[セキュリティ グループを作成、編集、削除する](/office365/admin/email/create-edit-or-delete-a-security-group)」を参照してください。

**Azure Active Directory サービス:** Azure Active Directory (AD) は、包括的な ID とアクセス管理機能をOffice 365に提供します。 開発者のために、ディレクトリ サービス、高度な ID ガバナンス、アプリケーション アクセス管理、機能豊富な標準ベースのプラットフォームを組み合わせています。 Office 365の AD 機能の詳細については、「[サインイン ページのブランド化とクラウド ユーザーのセルフサービス パスワード リセット](https://go.microsoft.com/fwlink/?linkid=2144147)」を参照してください。 [Azure Active Directory の Free、Basic、Premium の各エディションの](/previous-versions/azure/dn532272(v=azure.100))詳細について説明します。

# <a name="support-help-and-training"></a>[**サポート、ヘルプ、トレーニング**](#tab/Support)

## <a name="support"></a>サポート

エンタープライズ、ビジネス、フロントライン、教育、政府機関向けの Microsoft 365 およびOffice 365サブスクリプションごとに、Microsoft サポートはグローバルな技術、販売前、課金、サブスクリプションのサポートを提供します。 サポートは、有料サブスクリプションと試用版サブスクリプションの両方で、オンラインでMicrosoft 365 管理センターと電話の両方で利用できます。 詳細については、「[Microsoft サポート オプション」を](/Office365/Admin/contact-support-for-business-products)参照してください。 テクニカル サポートにお問い合わせの場合は、「 [**Microsoft 365 for business サポートにお問い合わせください**](/Office365/Admin/contact-support-for-business-products)。 テクニカル サポートには、サード パーティのサービスやアドインのトラブルシューティングは含まれません。 [**Microsoft Community**](https://answers.microsoft.com/) で他のお客様から回答を見つける方法について説明します。

**サポート：** Microsoft 開発チームと運用チームは、お客様にビジネス継続性を提供する上で重要な役割を果たす専用サポート組織によって補完されています。 サポート スタッフはサービスおよびサービスに関連するアプリケーションに精通しており、Microsoft 社内のアーキテクチャ、開発、テストの専門家と直接やり取りします。 サポート組織は運用および製品開発チームと密接に協力することで、迅速な問題解決を実現し、お客様の声を反映するための窓口になります。 お客様からのフィードバックは、計画、開発、運用プロセスに役立てられます。 サポートの詳細については、 [サポート](/office365/servicedescriptions/office-365-platform-service-description/support) に関する記事を参照してください。

**オンラインの問題追跡のサポート:** お客様は、問題が解決されていることを知る必要があり、タイムリーな解決を追跡できる必要があります。 Microsoft 365 管理センターは、サポート用の単一の Web ベースのインターフェイスを提供します。 お客様はこのポータルを使用することで、サービス リクエストを追加および監視するとともに、Microsoft サポート チームからのフィードバックを受信できます。

**継続的なスタッフ サポートに支えられたセルフ ヘルプのサポート:** Microsoft では、Microsoft のサポートを必要とせずに、サービス関連の問題を解決するのに役立つさまざまなセルフ ヘルプ リソースとツールを提供しています。 お客様は、サービス リクエストを作成する前にサポート技術情報の記事や FAQ を参照することで、よくある問題に関するヘルプを即座に得ることができます。 これらのリソースは絶えず最新の情報に更新され、既知の問題に対する解決策をタイムリーに提供します。 また、サポート担当者による対応が必要な問題が発生した場合は、電話または管理ポータルを通じて、24 時間 365 日体制のスタッフによる迅速な支援を得ることができます。

**管理者のサポート:** 承認された管理者は、Microsoft 365 管理センターを使用して、サービス要求をオンラインで送信したり、サポート電話番号にアクセスしたり、開いているサービス要求と最近閉じたサービス要求をすべて表示したりできます。 管理センターで送信されたサービス要求は、要求が閉じられた後、最大 14 日間再度開くことができます。 手順については、 [Microsoft 365 for business サポートにお問い合わせください](/Office365/Admin/contact-support-for-business-products)。

**Microsoft 365 のサポート:** Microsoft 365 テクニカル サポート チームは、Microsoft 365 とOffice 365に関連する問題のみをトラブルシューティングします。 顧客ネットワークに起因する問題はサポートの境界外にあり、このような場合、お客様はネットワーク チームと連携するか、 [Microsoft Networking チーム](https://support.microsoft.com/gp/contactus81?Audience=Commercial) にサポートを依頼する必要があります。

**コミュニティとセルフサービスのサポート オプション:** セルフサービスサポートはすべてのプランで利用でき、トラブルシューティング ツールとビデオ、ヘルプ記事やビデオ、 [Microsoft 365 コミュニティ](https://go.microsoft.com/fwlink/p/?LinkID=279811)のフォーラムや Wiki が含まれます。 セルフサービス サポート リソースの詳細については、 [ヘルプとトレーニング](/office365/servicedescriptions/office-365-platform-service-description/help-and-training) サービスの説明を参照してください。

**販売前のサポート:** 販売前のサポートは、サブスクリプションの機能と特典、プランの比較、価格とライセンスに関する支援を提供し、ビジネス ニーズを満たす適切なソリューションを特定するのに役立ちます。 また、販売前サポートでは、パートナーの紹介、購入、試用版のサインアップに関する支援も行います。 月曜日から金曜日までの営業時間内に問い合わせることができます。 販売前サポートには、テクニカル サポートと同じ電話番号を使ってアクセスできます。 サポート電話番号は、無料試用版の管理センターにあります。 手順については、 [Microsoft 365 for business サポートにお問い合わせください](/Office365/Admin/contact-support-for-business-products)。

**課金とサブスクリプション管理のサポート:** 課金とサブスクリプション管理の問題に関するサポートは、月曜日から金曜日までの現地営業時間中にオンラインまたは電話で入手できます。 課金およびサブスクリプション管理のサポートには、テクニカル サポートと同じ電話番号とオンラインのサービス要求プロセスを使ってアクセスできます。 サポート電話番号は、管理センターにあります。 手順については、 [Microsoft 365 for business サポートにお問い合わせください](/Office365/Admin/contact-support-for-business-products)。 課金とサブスクリプション管理の問題の例を次に示します。試用版へのサインアップまたはサブスクリプションの購入、試用版サブスクリプションから有料サブスクリプションへの変換、課金の概要、サブスクリプションの更新、ライセンスの追加または削除、有料サブスクリプションの取り消し。

**テクニカル サポート:** Microsoft 365 サブスクリプションのテクニカル サポートでは、基本的なインストール、セットアップ、および一般的な技術的使用に関するサポートが提供されます。 次の表に、サポート内容の一例を示します。

| サポート カテゴリ | 例 |
|:-----|:-----|
|インストールとセットアップ  <br/> | Exchange Online:  <br/>  メールボックスの移行  <br/>  受信者の構成 (メールボックスのアクセス許可、メール転送の構成、共有メールボックスの構成)  <br/>  自動検出の構成  <br/>  SharePoint Online:  <br/>  アクセス許可およびユーザー グループ  <br/>  ゲストの構成  <br/>  Skype for Business Online:  <br/>  インストールおよび連絡先の作成  <br/>  Microsoft 365 Apps for enterprise: インストールとセットアップのサポート  <br/> |
|構成  <br/> | サービスの構成の不具合  <br/>  プロビジョニングに関する問題  <br/>  ドメインの設定と再委任  <br/>  サービス構成の問題  <br/>  シングル サインオン (SSO)  <br/>  Active Directory の同期  <br/> |

**テクニカル サポートケースの処理:** Microsoft は、問題の種類と顧客への影響の評価に基づいて、ケースが開かれるときに重大度レベルを割り当てます。 次の表に、問題のタイプと重大度レベルの例を示します。

| 重大度レベル | 操作とサポートの説明 | 例 |
|:-----|:-----|:-----|
|重大度 A (重大)  <br/> |1 つまたは複数のサービスにアクセスできないか、または使用できない。実稼動、業務、または展開の期日に重大な影響を及ぼすか、実稼動や収益に重大な影響が生じる。複数のユーザーまたはサービスに影響が生じる。  <br/> | メールの送受信に関する広範囲の不具合。  <br/>  SharePoint サイトのダウン。  <br/>  すべてのユーザーがインスタント メッセージの送信、Skype for Business 会議のへ参加や予定、または Skype for Business 通話を行うことができない。  <br/> |
|重大度 B (高)  <br/> |サービスは使用できるが、一部に不具合がある。ビジネスへの影響は重大でないため、業務時間中に対処することができる。個別のユーザー、顧客、またはサービスが部分的に影響を受ける。  <br/> | Outlook の [送信] ボタンの文字が正しく表示されない。  <br/>  EAC (Exchange 管理センター) からは設定できないが、PowerShell からは設定できる。  <br/> |
|重大度 C (重大でない)  <br/> |ビジネスへの影響は軽微。 この問題は重要ですが、現在のサービスや生産性に大きな影響はありません。 個別のユーザーに部分的な影響が出ているが、別の方法が使用できる。  <br/> | ユーザーのパスワードを無期限に設定する方法。  <br/>  Exchange Online でユーザーが連絡先の情報を削除できない。  <br/> |

**テクニカル サポートの初期応答時間:** 最初の応答時間は、上記の重大度レベルとサブスクリプションの種類に基づいています。 次の表に、応答時間の目安を示します。

| 重大度レベル | Microsoft 365 Business Basic <sup>1</sup><br> Microsoft 365 Apps for business <sup>1</sup><br> Microsoft 365 Business Standard <sup>1</sup><br> Microsoft 365 Business Premium <sup>1</sup> | すべての Microsoft 365 およびOffice 365 Enterprise (E)<br/> フロントライン (F)<br/> 政府機関 (G)、および<br/> 教育機関 (A) プラン | 管理者特権でのサポート オプション<sup>3</sup> |
|:-----|:-----|:-----|:-----|
| 重大度 A (重大)  <br/> |連絡可能24 時間 365 日<sup>4</sup> <br/> 応答時間:1 時間  <br/> |連絡可能24 時間 365 日<sup>4</sup> <br/> 応答時間:1 時間  <br/> |連絡可能24 時間 365 日<sup>4</sup> <br/> 応答時間:1 時間  <br/> |
|重大度 B (高)  <br/> |使用可能:勤務時間  <br/> 応答時間:不定  <br/> |連絡可能24 時間 365 日<sup>4</sup> <br/> 応答時間:翌日  <br/> |連絡可能24 時間 365 日<sup>4</sup> <br/> 応答時間:2 時間  <br/> |
|重大度 C (中)  <br/> |使用可能:勤務時間  <br/> 応答時間:不定  <br/> |連絡可能24 時間 365 日<sup>4</sup> <br/> 応答時間:不定  <br/> |連絡可能24 時間 365 日<sup>4</sup> <br/> 応答時間:4 時間  <br/> |

<sup>1</sup> ビジネス プランには、重大でないすべての問題に対する営業時間サポートと、Microsoft からの 24 時間 365 日の電話サポートが含まれます。<br/>
<sup>2</sup> エンタープライズ プランには、すべての問題に対する Microsoft からの 24 時間 365 日の電話サポートが含まれています。<br/>
<sup>3</sup> 管理者特権でのサポート オプションの説明については、「 [その他のサポート オプション](/office365/servicedescriptions/office-365-platform-service-description/microsoft-365-office-365-general-information?tabs=Support)」を参照してください。<br/>
ほとんどの国と地域では、<sup>4</sup> つの通話とサービス要求が 24 時間、週 7 日処理されます。

**スタンドアロン プランのサポート:** 有料スタンドアロン プランのサポートは、Enterprise サービス ファミリのプランと同じレベルのサポートと応答時間の目標で処理されます。 スタンドアロン プランの一覧については、「[スタンドアロン サービス](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options#standalone-services)」を参照してください。

**テクニカル サポート言語:** 場所と言語に応じて、サポート エンジニアは、ほとんどの地域の営業時間と、場合によっては 24 時間単位で利用できます。 詳細については、「[国際電話番号](/Office365/Admin/contact-support-for-business-products)と[Microsoft サポートオプション](https://products.office.com/business/office-365-for-business-support-options)」を参照してください。 追加の翻訳サポートが必要な場合は、サポート エンジニアが行に残り、翻訳者が通話に参加できるように手配することができます。

**Business Assist for Microsoft 365:** Business Assist for Microsoft 365は、小規模企業向けに設計されており、オンボーディングから日常的な使用まで、ビジネスを成長させる際に、中小企業の専門家に 24 時間体制でアクセスできます。 詳細については[、Business Assist for Microsoft 365を参照](/microsoft-365/admin/misc/business-assist)してください。

**共有サポートの責任:** Microsoft は、資格のある専門家からタイムリーなテクニカル サポートを受けるのがクラウド サービスの重要な側面であることを理解しています。 同様に、お客様の IT 部門もユーザー サポートにおいて非常に重要な役割を担っていると理解しています。

**管理者の責任:** Microsoft 管理者ロールを持つPeopleは、管理センターの **管理** セクションにアクセスし、サービス要求を Microsoft に送信し、サービス要求について Microsoft と直接通信することを承認された顧客の組織内の唯一のユーザーです。 エンタープライズプランとMicrosoft 365 AppsプランのOffice 365を使用すると、さまざまな機能を果たす複数の種類の管理者を指定できます。 このサービスの説明では、管理者という一般的な肩書きで、すべてのカテゴリの管理者を表しています。 管理者の役割の詳細については、「[Office 365 で管理者ロールを割り当てる](/office365/admin/add-users/assign-admin-roles)」を参照してください。

**管理者ロール**: 管理者は、各サービス ユーザーを設定してサポートする主要な連絡先です。 管理者は、サービスの管理とアカウントのメンテナンスを担当し、ユーザーがサービスへのアクセスを許可するユーザー アカウントの設定と構成を提供し、クライアント接続、クライアント ソフトウェア、およびモビリティのインストールの問題に対処し、顧客の組織の管理範囲内でサービスの可用性の問題に対処し、Microsoft のセルフサービス サポート リソースを使用してサポートの問題を解決します。 管理者はお客様のユーザーに対して初期の支援を提供する必要があります。 ただし、管理者がセルフサービス サポート リソースの助けを借りて問題を解決できない場合は、 [テクニカル サポート](/office365/servicedescriptions/office-365-platform-service-description/support#technical-support)にお問い合わせください。

Office 365 for Enterprise は、役割ベースのアクセス制御 (RBAC) モデルに従います。アクセス許可と機能は、管理者の役割によって定義されます。 自分の組織の Office 365 にサインアップすると、自動的に全体管理者または最上位管理者になります。 管理者の役割には、グローバル管理者、課金管理者、パスワード管理者、サービス管理者、およびユーザー管理の管理者の 5 つがあります。 Exchange Online、SharePoint Online、Skype for Business Online の管理への適用方法など、Office 365 for Enterprise の管理者の役割の詳細については、「[管理者ロールを割り当てる](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/jj878348(v=ws.11))」を参照してください。 中国で 21Vianet によって運用されているOffice 365を使用している場合は、「[ビジネス向けのOffice 365で管理者ロールを割り当てる](/office365/admin/add-users/assign-admin-roles)」を参照してください。

**パートナーの委任された管理とサポート:** パートナーは、顧客に代わってアカウントを管理する権限を与えることができます。 顧客は、パートナーが使用するユーザー アカウントを必要とせず、委任された管理権限を付与するときにライセンスを使用しません。 パートナーは、無制限のアクセスまたは制限付きのアクセスを組織内のユーザーに割り当てることができます。 制限付きアクセスには、パスワードのリセット、サービス要求の管理、サービスの正常性の監視の権限が含まれます (委任された管理者としてパートナーを使用して指定する機能は、リージョンによって異なります)。

**Microsoft サポート ロール:** Microsoft サポートの役割は、お客様の問題とエスカレーションに関する技術的なガイダンスのトラブルシューティングと提供、特定のサービス要求に関連する情報の収集と検証、問題の調整と解決管理の提供、管理者とのコミュニケーションを維持して、継続的に問題に対処できるように支援すること、ライセンス、請求、サブスクリプションに関する問い合わせに関するサポートを提供し、購入と試用版の問い合わせに対する支援を提供することです。 アンケートを通じてサービスを改善する方法に関する顧客のフィードバックを継続的に収集します。

**管理者特権でのサポート オプション:** Microsoft に含まれるサポート サービスは多くのお客様のニーズを満たしていますが、より高度な要件または複雑な環境をお持ちのお客様は、Microsoft からの有料サポート オプションを検討する必要があります。 上級サポート サービスは、さらに短い時間での対応、問題の重大度レベルの設定、およびその他の技術的リソースの利用やサポート用アカウントの管理にも対応しています。 管理者特権でのサポートの例には、サービス更新プログラムの管理が含まれます。クライアントとサービスのエンドツーエンドのサポート。高度なエンジニアによる事後対応サービスとアドバイザリ サービス。インシデント管理とオンサイト ワークショップ。

**その他のサポート サービス:** 利用可能な追加サポート サービスには、いくつかの種類があります。Office 365への移行をサポートするフル ライフサイクル サービスを探している大企業のお客様向けのオプションについては、「[従業員の生産性を高める」](https://www.microsoft.com/en-us/microsoftservices/cloud-productivity.aspx)を参照してください。オンライン サービスへのアクセスに必要な Microsoft とオンプレミスの両方のテクノロジをカバーするマネージド サポート サービスを探している大企業のお客様向けのオプションについては、「」を参照してください。 [Premier Support](https://www.microsoft.com/enterprise/services/support): 米国、カナダ、英国の小規模企業のお客様向けのオプションについては、「[プロフェッショナル ダイレクト サポート](https://support.microsoft.com/help/4341255/support-for-business)」を参照してください。

**パートナー：** Microsoft パートナーを選択し、サービス要求チケットの作成を含む管理機能を委任できます。 詳しくは、[パートナー](/office365/servicedescriptions/office-365-platform-service-description/partners) サービスの説明、および「 [サブスクリプション アドバイザー パートナーを追加、変更、または削除する](/office365/admin/misc/add-partner)」を参照してください。

**開発者：** 開発者は、 [MSDN Microsoft Developer Network](https://developer.microsoft.com/office/docs) で Office および SharePoint アプリケーションの開発について詳しく学習できます。 開発者向けサポートは、開発者コミュニティのオンライン ブログやフォーラム、Premier サポート リソースまたはパートナー サポート リソースを通じて、または Microsoft を通じて直接入手できます。 開発者サポート オプションへのリンクについては、「 [サポート リソース](https://developer.microsoft.com/office/docs)」を参照してください。

**ボリューム ライセンス**: ボリューム ライセンス プログラムで Microsoft からライセンスを既に購入している場合は、次の場所でサポートを受けることができます。ライセンスとキーの検索に関連するサポートについては、 [ボリューム ライセンス サービス センター](https://www.microsoft.com/licensing/servicecenter/default.aspx)にアクセスしてください。テクニカル サポートについては、 [テクニカル サポート](/office365/servicedescriptions/office-365-platform-service-description/support#technical-support)を参照してください。課金に関する質問については、「 [課金とサブスクリプション管理のサポート](/office365/servicedescriptions/office-365-platform-service-description/support#billing-and-subscription-management-support)」を参照してください。ボリューム ライセンスの一般的な情報については、 [ボリューム ライセンスに関するページ](https://www.microsoft.com/licensing/default)を参照してください。

> [!NOTE]
>
> Microsoft チームはスクリプト (JavaScript、VBScript などのスクリプト手法、VBA など) をサポートしていません。 スクリプトのサポートが必要な場合は、[**Microsoft サポート**](https://support.microsoft.com/)にお問い合わせください。 Office アプリケーションの使用状況のサポートについては、「 [**サブスクライバーの Microsoft Office アプリケーションの問題に関するサポート オプション」を参照してください**](https://support.office.com/article/support-options-for-microsoft-office-application-issues-for-office-365-subscribers-0a02cd18-19be-4cfa-b430-3b53ea26920f)。

## <a name="help-and-training"></a>Help and training

Microsoft Office 365には、次のヘルプとトレーニング リソースが用意されています。 コミュニティ リソースは、Office 365 の各国版に当てはまります。 21Vianet によって運用されているOffice 365を使用している場合は、WeChat を使用できます。 [**21Vianet によって運用されているOffice 365の技術、課金、サブスクリプションのサポートを取得**](/microsoft-365/admin/contact-support-for-business-products)し、QR コードのページの下部までスクロールする方法に関するページを参照してください。

**オンライン ヘルプ:** ヘルプ記事とビデオは、Office 365 ポータルの上部ナビゲーション バーのヘルプ アイコンやMicrosoft 365 管理センターなど、サービス内の任意のインライン ヘルプ リンクから入手できます。 また、すべてのOffice 365ヘルプを[https://office.microsoft.com](https://go.microsoft.com/fwlink/p/?LinkId=272056)検索することもできます。

**トレーニング：** トレーニングは、ビデオ、録画されたライブ イベント、認定につながるクラスを通じて利用できます。 詳細については、「 [Microsoft 365 の基本ビデオ トレーニング](https://support.microsoft.com/office/microsoft-365-basics-video-training-396b8d9e-e118-42d0-8a0d-87d1f2f055fb)、 [Microsoft 365 トレーニング](https://support.microsoft.com/training)、 [管理者と IT 担当者向け](/learn/m365/)、 [小規模企業向けの](/microsoft-365/admin/admin-video-library) Microsoft 365 トレーニング」を参照 [してください。完全なラーニング カタログを参照し](/learn/browse/)、 [Microsoft 認定を取得](/learn/certifications/)し、 [すべての学習オプションを参照](/learn/browse/)し、 [ライブ イベントと録画イベントを視聴](/learn/tv/)します。

**コミュニティ：** Office 365 コミュニティは、セルフ ヘルプ サポート情報の単一の宛先です。 コミュニティには、お客様がサポート フォーラム、Wiki、およびブログを通じて、技術、課金、サービスに関するさまざまな質問の答えを見つけられるように、最新の情報が掲載されています。 サポート フォーラムは、Microsoft サポート代理人によってスタッフが配置され運営されています。 Office 365 コミュニティのホーム ページから、フォーラム、Wiki、ブログの各リソースにアクセスできます。 詳細については、[Office 365 コミュニティ](https://techcommunity.microsoft.com/)をご覧ください。

**フォーラム：** フォーラムは、テクニカル サポートの質問を投稿したり、Office 365 サービスに関連するトピックについて話し合うことができるオンラインの宛先をコミュニティ参加者に提供することを目的としています。 利用可能なフォーラムは、Office 365、ディレクトリ統合サービス、Office 365のドメイン、ダウンロード、Emailと予定表、IM、会議と会議、Office 365の管理、プロジェクトの管理、モバイル アクセス、Office 365 for Mac、Office アプリ、サイトとドキュメント共有、セキュリティ センタードキュメント、Office 365、Yammer にアップグレードする

**ウィキ：** Wiki には、Microsoft の従業員と認証されたコミュニティ メンバーによって作成された Wiki ページが含まれます。 この共同作業のサイトには、特定の Office 365 の技術的なシナリオについて収集された最新のコンテンツが網羅されています。 通常、個々の Wiki ページには、特定の技術的なシナリオに関する Web サイト、Web キャスト、トラブルシューティング ビデオ、FAQ ページ、ドキュメント、およびダウンロードへのリンクが含まれています。 各改定日の履歴追跡と作成者のエイリアスがバージョン比較機能とともに提供されています。

**ブログ**: Office 365技術ブログは、Office 365 オンライン サービスに関する現在の情報を取得し、Office 365機能の利点について学習するための優れたリソースです。 トピックには、製品に関する見識、新製品の発表、お客様のインタビュー、ゲストのブログ シリーズなどがあります。

**Office 365ガイダンスを管理する:** 大規模な組織の IT プロフェッショナルは、Office 365ドキュメントの管理のホーム ページにアクセスできます。 このページでは、大規模な組織向けの複雑なデプロイ ガイダンスへのリンクを提供します。 詳細については、「[Office 365の管理」を](/Office365/)参照してください。

**その他のセルフ ヘルプ リソース:** Office 365 コミュニティとオンライン ヘルプに加えて、Office 365には、Office 365のトラブルシューティング ツール、テクニカル サポート ビデオ、ソーシャル メディアなどのセルフ ヘルプ リソースが含まれています。

**Office 365 のトラブルシューティング ツール** Office 365 のトラブルシューティング ツールは、ユーザーが問題に関する一連の短い質問に回答した後、その回答に基づいて有用なツールと情報を提示します。 このツールを使用するには、Office 365 コミュニティの[管理者および IT プロフェッショナル向けの Office](/office365/troubleshoot/) トラブルシューティングページに移動します。

**テクニカル サポート ビデオ** 英語版の教育用トラブルシューティング ビデオは、よくあるユーザーからの質問に基づいて開発されています。35 種類以上の個々のビデオがあり、毎週さらに追加されています。トピックは、BlackBerry® 管理センターの概要からディレクトリ同期のアクティブ化および移行まで広範にわたっています。これらのビデオを視聴するには、Office 365 コミュニティ サイトでビデオを検索してください。コミュニティ ポータルを通じてビデオのリクエストを送信することをお勧めします。また、 [Office 365 YouTube](https://go.microsoft.com/fwlink/?LinkId=272059) および [ショーケース](/office365/servicedescriptions/office-365-service-descriptions-technet-library) チャンネルでもビデオを検索できます。

**ソーシャル メディア**[Facebook](https://go.microsoft.com/fwlink/?LinkId=272061)、[Twitter](https://go.microsoft.com/fwlink/?LinkId=272062)、および [LinkedIn](https://www.linkedin.com/groups/Microsoft-Office-365-3724282?itemaction=mclk&anetid=3724282&impid=&pgkey=anet_search_results&actpref=anetsrch_name&trk=anetsrch_name&goback=%2Egdr_1307137875158_1) で Office 365 をフォローすることで、お客様とパートナーは Office 365 についてより多くのことを学習する、さらなる手段を得ることができます。この Office 365 についてすばやく簡単に学習する方法によって、他のユーザーの意見を聞き、自分のコメントを追加してツイートできます。Microsoft サポート プロフェッショナルが、Microsoft 関連の Facebook および Twitter のアクティビティをモニターし、サポート関連の問い合わせについて支援しています。最新のツイートと最新の Facebook フィードを検索するには、Office 365 コミュニティ ホームページの下部に移動し、お客様とパートナーの日々のディスカッションを確認してください。

**言語：** オンライン ヘルプ記事、Wiki とブログ、フォーラム、テクニカル センター、トラブルシューティングは、さまざまな言語で入手できます。

**オンライン ヘルプ記事の言語:** ブルガリア語、簡体字、繁体字、チェコ語、デンマーク語、オランダ語、エストニア語、フィンランド語、フランス語、ドイツ語、ギリシャ語、ハンガリー語、イタリア語、日本語、韓国語、ラトビア語、リトアニア語、ノルウェー語、ポーランド語、ポルトガル語、ポルトガル語ブラジル、ルーマニア語、ロシア語、セルビア語、スロバキア語、スロベニア語、スペイン語、スウェーデン語、タイ語、トルコ語、ウクライナ語。

**Wiki とブログの言語:** アラビア語、簡体字、繁体字中国語、デンマーク語、オランダ語、フランス語、ドイツ語、イタリア語、日本語、韓国語、ノルウェー語、ポーランド語、ポルトガル語-ブラジル語、ロシア語、スペイン語、スウェーデン語。

**フォーラムの言語:** 簡体字、繁体字、フランス語、ドイツ語、イタリア語、日本語、韓国語、ポーランド語、ポルトガル語-ブラジル語、ロシア語、スペイン語。

**Tech Center の言語:** 簡体字、繁体字、フランス語、ドイツ語、イタリア語、日本語、韓国語、ポルトガル語-ブラジル語、ロシア語、スペイン語。

**トラブルシューティング用の言語:** 簡体字、繁体字、フランス語、ドイツ語、イタリア語、日本語、韓国語、ポーランド語、ポルトガル語-ブラジル語、ロシア語、スペイン語。

# <a name="domains-networking-and-partners"></a>[**ドメイン、ネットワーク、パートナー**](#tab/Domains)

## <a name="domains"></a>ドメイン

**ドメイン**: ドメインを追加すると、ステップ バイ ステップ ウィザードを使用してユーザーを追加し、電子メール アドレスやその他のサービスをビジネス名に変換できます。 ウィザードを完了すると、現在の電子メール プロバイダーに移動する代わりに、ビジネス メールが Microsoft に届き始めます。 詳細については、「 [Microsoft にユーザーとドメインを追加する」を参照してください](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611)。 21Vianet が運用している Office 365 を使用する場合は、「[ドメインを確認する](/office365/admin/setup/add-domain)」を参照してください。

**カスタム ドメイン:** サブスクリプションには最大 5,000 個のドメイン (サブドメインを含む) を追加できます。 別の Microsoft クラウド サービスで既に使用しているドメインを Microsoft 365 に追加することはできません。 この制限は、同じドメインを複数のサブスクリプションに追加できないことも意味します。 詳細については、「[ドメインに関する FAQ](https://support.office.com/article/Domains-FAQ-1272bad0-4bd4-4796-8005-67d6fb3afc5a)」を参照してください。

新しいユーザーを作成する場合、ユーザーのサインイン名と電子メール アドレスは、Microsoft 365 管理センターで設定される既定のドメインに割り当てられます。 詳細については、「[ユーザーとドメインを追加する](https://support.office.com/article/Add-your-users-and-domain-to-Office-365-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)」を参照してください。 既定では、 サブスクリプションは、 アカウントで作成された <*会社名*>**.onmicrosoft.com** ドメインを使用します。 Office 365 におけるドメインの詳細については、「[ドメイン](/office365/servicedescriptions/office-365-platform-service-description/domains)」のサービスの説明を参照してください。 * 中国で 21Vianet が運用している Office 365 を使用している場合、既定のドメインは、<*companyname*>**.onmsChina.cn** です。

**ドメインの追加:****onmicrosoft.com** ドメインを保持するのではなく、Microsoft に 1 つ以上のカスタム ドメインを追加し、検証済みドメインでサインインするようにユーザーを割り当てることができます。 Each user's assigned domain is the email address that will appear on sent and received email messages. それぞれが別々の名前空間で表現される最大 900 の登録済みインターネット ドメインをホストできます。

**2 番目と 3 番目のレベルのドメイン:** Office 365 EnterpriseとMicrosoft 365 Apps for businessを使用すると、marketing.contoso.com などの第 3 レベルのドメインを含む任意のレベル ドメインを追加できます。 [Microsoft へのカスタム サブドメインまたは複数のドメインの追加に関するページを参照してください](/office365/admin/setup/domains-faq)。 21Vianet によって操作されるOffice 365を使用している場合は、「[21Vianet によって運用Office 365カスタム サブドメインまたは複数のドメインを追加する](/office365/admin/setup/domains-faq)」を参照してください。

**ドメイン検証 DNS レコード:** Microsoft 365 を使用すると、DNS ホスティング プロバイダーですべての DNS レコードを管理したり、Microsoft がドメインの DNS レコードを設定して管理したりすることができます。 レコードを引き続き管理する場合は、必要に応じて Microsoft サービスを指すように特定のレコードを変更します。 Microsoft がドメインの DNS レコードを管理している場合は、最初にドメインのネームサーバー レコードを Microsoft を指すように切り替え、Microsoft がサービスを設定してから、ドメインの DNS レコードが Microsoft で管理されるようにする必要があります。

**ドメイン レジストラー:** 各レコードに使用する特定の値を含め、レコードを追加するための詳細な手順を示すドメイン レジストラーの一覧については、「[DNS レコードの作成](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)」を参照するか、21Vianet で運用されているOffice 365を使用している場合は、21Vianet によって運用されるOffice 365の DNS レコードの作成に関するページを参照してください。 ドメインが GoDaddy に登録されている場合、Microsoft は GoDaddy で必要なレコードを作成できます。

**DNS レコードの管理:** DNS レコードがホストされている場所に関係なく、Microsoft または別のホスティング プロバイダーでホストされているパブリック Web サイトの URL にドメインを使用するように DNS レコードを設定できます。 Microsoft は、DNS レコードを事前にチェックして、DNS の問題を見つけて解決します。 DNS レコードが想定したものと一致しない場合は、Microsoft 365 管理センターに通知が表示され、特定された可能性のある問題を修正する方法を示す情報が表示されます。 詳細については、「[Microsoft が DNS レコードを管理する方法](/office365/admin/setup/domains-faq)」を参照するか、21Vianet によって運用Office 365については、「[DNS レコードを管理するときにOffice 365の DNS レコードを作成する](/office365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records)」を参照してください。

**ドメインの共有:** Microsoft のドメインの一部のメール アドレスと、以前の電子メール プロバイダーのメール アドレスの一部をパイロットできます。 これは、追加のセットアップ手順が必要であり、Microsoft サービスにはいくつかの制限があるため、パイロットの間にのみ使用することをお勧めします。 詳細については、「 [小規模ビジネス向けのパイロット Microsoft 365](https://support.office.com/article/39cee536-6a03-40cf-b9c1-f301bb6001d7) と [適格性 - FastTrack – Microsoft 365」を](/fasttrack/eligibility)参照してください。

## <a name="networking"></a>ネットワーク

Microsoft では、次のネットワーク機能がサポートされています。

**ポート、プロトコル、および IP アドレス:** Microsoft では、IPv4 アドレスと IPv6 アドレスが使用されます。 IPv6 の使用は任意で、Office 365 との接続には必要ありません。 すべての Microsoft 365 機能が IPv6 を使用して完全に有効になっているわけではありません。 Ipv6 サポートの詳細については、 [Microsoft サービスでの IPv6 サポートに関するページを](/office365/enterprise/ipv6-support)参照してください。

**IP アドレス:** Microsoft では、Microsoft ヘルプで許可されている IP アドレスの一覧を保持しています。 詳細については、「 [URL と IP アドレス範囲」を](/office365/enterprise/urls-and-ip-address-ranges)参照してください。 21Vianet が運用している Office 365 については、「[21Vianet が運用している Office 365 の URL と IP アドレス](/office365/enterprise/managing-office-365-endpoints)」を参照してください。

> [!IMPORTANT]
>
> 特定の IP アドレス サブネットにルーティングするのではなく、上記の記事に記載されているルート ドメイン名 (*.Outlook.com、*.MicrosoftOnline.com、*.SharePoint.com など) へのルーティングを有効にすることを強くお勧めします。 IP アドレス サブネットを使用すると、変更が行われたときにユーザーに対するサービスが停止する危険があります。

**帯域幅の要件:** 帯域幅の要件については、「 [インターネット帯域幅の計画](/office365/enterprise/network-planning-and-performance)」を参照してください。

**Microsoft への接続:** Microsoft へのすべての接続は、パブリック インターネット経由またはプライベート Azure ExpressRoute 接続経由で行われ、必要に応じて SSL によってセキュリティで保護されます。 Azure ExpressRoute を使用すると、インターネットをバイパスして、グローバル Microsoft ネットワークに直接接続できます。 Microsoft ネットワーク パートナーは、グローバル Microsoft ネットワークへの接続を提供します。 Azure ExpressRoute の詳細については、「[azure ExpressRoute for Office 365」を](/microsoft-365/enterprise/azure-expressroute)参照してください。

**WAN アクセラレータ:** Microsoft では、Office 365を使用した顧客所有の WAN アクセラレーションとキャッシュ デバイスのサポートは提供されていません。 高待機時間または低帯域幅の条件下で WAN 最適化コントローラーを使用してパフォーマンスを向上させる場合は、Microsoft でのサービス要求のトラブルシューティング中に無効にし、デバイス サポートのためにデバイス ベンダーと協力する必要があります。 詳細については、「OFFICE 365を[使用した WAN アクセラレーションとキャッシュ デバイス](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365)」を参照してください。

**Microsoft Global Network:** Microsoft ネットワーク インフラストラクチャは、データ センター、サーバー、コンテンツ配布ネットワーク、エッジ コンピューティング ノード、光ファイバー ネットワークの大規模なグローバル ポートフォリオで構成され、サービスのグローバル配布を提供します。 高度なサービスインストルメンテーションと監視は、各コンポーネントと最も深いレベルで統合され、データ センター、ネットワーク バックボーン、インターネット交換などを可視化し、発生する中断の原因を特定、診断、管理するのに役立ちます。 ネットワークは、大規模なネットワーク障害が発生した場合でも、パフォーマンスを低下させることなく、十分な処理能力を維持できるように構成されています。 詳細については、 [Microsoft Global Network](/azure/networking/microsoft-global-network) に関するページを参照してください。

**コンシューマー サービス ネットワーク:** 顧客データの機密性と整合性を維持するために、Microsoft はコンシューマー サービス ネットワークを Microsoft ネットワークから分離します。 物理的な分離、論理的な分離、ファイアウォール、プロトコルの制限など、情報フローを制御するために複数の手法が使用されます。 詳細については、「[Office 365 セキュリティ センター](https://www.microsoft.com/trust-center)」を参照してください。

**物理的な分離:** ネットワーク セグメントは、特定の通信パターンを防止するように構成されたルーターによって物理的に分離されます。

**論理的な分離:** 仮想 LAN (VLAN) テクノロジは、通信をさらに分離するために使用されます。

**ファイアウォール：** ファイアウォールやその他のネットワーク セキュリティ適用ポイントは、インターネットに公開されているシステムとのデータ交換を制限し、Microsoft によって管理されているバックエンド システムからシステムを分離するために使用されます。

## <a name="partners"></a>パートナー

Microsoft Office 365 は正規の Microsoft パートナーとして、カスタマーの基盤を発展させ、カスタマーとの持続的な関係を築く機会を提供します。 カスタマーは月会費または年会費を支払うことでクラウドベースのサービスを使用することができ、データのバックアップ、サーバー ハードウェア、サーバーのアップデートなどの管理をする必要がなくなります。 利用可能なサービスは、提供が承認されているサービスの種類によって異なります。

**パートナーの機能:** パートナー機能を使用する方法の詳細については、「[**ビジネスを構築し、Office 365 パートナー サブスクリプションを管理**](https://go.microsoft.com/fwlink/?LinkID=271614&clcid=0x409)し、パートナー機能のプレゼンテーションを確認する」を参照してください。 パートナー機能へのアクセスを受け取るには、 [**Microsoft Online Services パートナー契約**](https://go.microsoft.com/fwlink/p/?LinkId=285473)に署名して Cloud Essentials に参加できます。

> [!NOTE]
>
> 次に記載されているパートナー機能は、21Vianet が運用している Office 365 で使用可能です。

**試用版の招待と発注書を作成します。** Office 365の **パートナーの概要** ページを使用して、顧客がOffice 365を試すことができるように、試用版の招待を作成して顧客に送信できます。 招待には申し出に応じて 1 つまたは複数のサービスを含めることができます。 代理管理の提供が認められている場合には、試用版への招待にオプションを追加し、カスタマーの代理としてアカウントを管理することができます。 これによりカスタマーがOffice 365 を試用しやすくなります。

**試用版への招待:** 顧客にOffice 365の試用版の招待を送信した後は、特定のサービスや顧客が必要とするライセンスの数など、顧客のニーズに合わせてカスタマイズされた購入オファーを作成して送信することでフォローアップできます。 代理管理の提供が認められている場合には、購入プランにオプションを追加し、カスタマーの代理としてアカウントを管理することができます。

**委任された管理を提供します。** 代理管理を使用すると、パートナーは、すべての顧客のサービスとサブスクリプションに対して完全な管理アクセス権を持つことができます。 つまり、カスタマーの代理として管理タスクを実行することができます (メールボックスの設定、ユーザーおよびグループの追加または削除、Microsoft カスタマー サービス サポートへのサービス要求の送信を含みます)。 代理管理機能は、Cloud Essentials、Cloud Accelerate、または Cloud Deployment プログラムに登録されているパートナーのみに提供されます。

**代理管理者:** 顧客のアカウントの管理を開始する前に、顧客は委任された管理者としてユーザーを承認する必要があります。 顧客の承認を得るために、代理管理用のオファーを送信します。これには、試用版の招待または購入オファーを含めることができます。 顧客は、パートナーの招待メールに応答することで代理管理パートナーを承認します。 カスタマーが代理として管理タスクを実行するパートナーを承認した場合にも、そのカスタマーは直接 Microsoft サポートに連絡を取ってサービス要求を送信することができます。

**委任されたパートナー:** 各顧客には、委任された管理パートナーを 1 人持つ権利があります。 このパートナーは、顧客のレコードパートナー (POR) にすることもできますが、そうする必要はありません。 登録パートナーと代理管理パートナーの役割は分離されており、カスタマーはそれぞれを別に指定します。 これにより、カスタマーは購入のアドバイスを得るためにあるパートナーを選択し、実装や管理されたサービスのために別のパートナーを選択することができます。 また、パートナーは、これらのロールの一方または両方に特化したビジネスを構築するかどうかを選択することもできます。

**Office 365 Marketplace で顧客や他のパートナーとつながる:** Office 365 Marketplace では、パートナー サービスと専門知識を見つける機会を顧客に提供します。 詳細については、「 [レコードまたは次のウィジェットを使用して顧客と接続](/dynamics365/sales/connect-with-customers) する」と「 [他のパートナーと連携する - パートナー センター](/partner-center/work-with-other-partners)」を参照してください。

**Microsoft パートナー ネットワーク:** Microsoft パートナー ネットワークは、パートナーのニーズに対応することに取り組んでいます。 マイクロソフト パートナー ネットワークに参加する、また Microsoft のパートナーへのサービスについて知るためには、「[マイクロソフト パートナー ネットワーク](https://go.microsoft.com/fwlink/?LinkID=272021&clcid=0x409)」を参照してください。

# <a name="privacy-security-rights-and-sla"></a>[**プライバシー、セキュリティ、権利、SLA**](#tab/Privacy)

## <a name="privacy-security-and-transparency"></a>プライバシー、セキュリティ、および透明性

Microsoft は、お客様とのパートナーシップを尊重し、お客様のデータのプライバシーとセキュリティの保護を重視しています。 詳細については、「[Microsoft Trust Center](https://go.microsoft.com/fwlink/?LinkID=717951&clcid=0x409)」をご覧ください。 この記事の情報は Office 365 の各国版に適用されます。 Office 365の国内クラウド インスタンス (Office 365米国政府を含む)、および 21Vianet によって運用されているOffice 365を使用している場合は、[**Microsoft National Cloud**](https://go.microsoft.com/fwlink/?linkid=841582) に関するページを参照してください。

**プライバシー：** Microsoft Office 365がデータのプライバシーを保護する方法については、「[プライバシー](https://go.microsoft.com/fwlink/?LinkID=717953&clcid=0x409)」ページを参照してください。 管理者がエンタープライズ、ビジネス、政府機関、教育機関のOffice 365プライバシー設定を構成するための具体的な手順については、「[管理者向けの高度なプライバシー オプション](https://go.microsoft.com/fwlink/p/?LinkID=285202)」を参照してください。

**他のサービスのセキュリティとプライバシー:** Microsoft 365 Apps for enterpriseを含む他の Microsoft サービスのセキュリティとプライバシーについては、「[セキュリティ センターはどのオンライン サービスに適用されますか?」を](https://www.microsoft.com/trustcenter/default.aspx)参照してください。

**セキュリティ：** Microsoft がOffice 365 サービスを安全かつ確実に提供する方法については、「セキュリティ」を参照 [してください](https://go.microsoft.com/fwlink/?LinkID=717954&clcid=0x409)。

**透明 性：** お客様は、お客様のデータがどこに存在するか、Microsoft でアクセスできるユーザー、および内部でその情報を使用して Microsoft が行う操作を確認できます。 詳細については、「[透過性](https://go.microsoft.com/fwlink/?LinkID=717955&clcid=0x409)」をご覧ください。

**Advanced eDiscovery:** 電子情報開示 (電子情報開示) は、訴訟の証拠として使用できる電子情報を特定して配信するプロセスです。 Advanced eDiscoveryは、Office 365の既存の電子情報開示機能のセットに基づいて構築されているため、大規模で構造化されていないデータ セットを分析し、訴訟に関連するデータの量を減らすことができます。 Office 365 コンプライアンス センターの検索機能を使用して、組織内のすべてのコンテンツ ソースの初回検索を実行し、特定の訴訟に関連する可能性のあるデータを識別および収集できます。 次に、高度な電子情報開示のテキスト分析機能、マシン学習機能、関連/予測コーディング機能を適用することによって、そのデータを分析できます。 詳細については、「[Advanced eDiscovery](/microsoft-365/compliance/overview-ediscovery-20)」を参照してください。

**カスタマー ロックボックス:** Microsoft 管理者は、カスタマー ロックボックスを使用して、Microsoft サポート エンジニアがヘルプ セッション中にデータにアクセスする方法を制御できます。 エンジニアが、トラブルシューティングや問題解決のためにデータにアクセスする必要がある場合は、カスタマー ロック ボックスを使用してアクセス要求を承認または拒否することができます。 承認すると、エンジニアはデータにアクセスできるようになります。 各要求には有効期限があり、問題が解決されると、要求は閉じられ、アクセスは取り消されます。 Customer Lockbox は、Office 365 Enterprise 5 プランに含まれているか、他のOffice 365 Enterprise プランで別のサブスクリプションを購入できます。 詳細については、「[カスタマー ロックボックス要求のOffice 365](/microsoft-365/compliance/customer-lockbox-requests)」を参照してください。

**Microsoft Defender for Office 365:** Defender for Office 365は、マルウェアやウイルスから組織を保護するのに役立ちます。 Defender for Office 365には、[安全なリンク](/office365/securitycompliance/atp-safe-links)、[安全な添付ファイル](/office365/securitycompliance/atp-safe-attachments)、[フィッシング詐欺対策](/office365/securitycompliance/atp-anti-phishing)、[スプーフィング インテリジェンス機能が](/office365/securitycompliance/learn-about-spoof-intelligence)含まれます。 Defender for Office 365の詳細については、[サービスの説明Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)参照してください。

[**安全なリンク**](/office365/securitycompliance/atp-safe-links)**と**[**安全な添付ファイル**](/office365/securitycompliance/atp-safe-attachments)**:** 安全なリンクは、メッセージ内の悪意のあるハイパーリンクからユーザーをプロアクティブに保護し、リンクが選択されるたびに保護を提供します。 安全な添付ファイルは、不明なマルウェアやウイルスから保護し、既知のウイルス/マルウェア署名を持たないすべてのメッセージと添付ファイルを、悪意のある意図を検出できる特別な環境にルーティングDefender for Office 365。

## <a name="product-use-rights"></a>製品使用権

**Microsoft Online Services 製品の使用権:** Microsoft Online サブスクリプション契約に準拠している場合、[ライセンス リソースとドキュメント](https://www.microsoft.com/licensing/docs)で明示的に許可されているように、オンライン サービスおよび関連ソフトウェアを使用できます。

**21Vianet 製品の使用権によって運用Office 365:** 21Vianet が運用するOffice 365に関する [21Vianet サービス レベル 契約](https://go.microsoft.com/fwlink/?linkid=846729)、[Online Services Standard Agreement](https://www.21vbluecloud.com/office365/O365-AgreeWebDir/)、[および使用条件](https://www.21vbluecloud.com/office365/O365-TOU/)を参照してください。 21Vianet が運用している Office 365 は、中国でのみ提供と運用が行われているサービスです。 このサービスには、Microsoft が 21Vianet に対してライセンスを与えたテクノロジが搭載されています。 詳細については、「[**21Vianet によって操作されるOffice 365について学習する」を参照**](/microsoft-365/admin/services-in-china/services-in-china?viewFallbackFrom=o365-worldwide)してください。

**ライセンス：** 組織のライセンス プログラムの詳細については、「 [ボリューム ライセンス](https://go.microsoft.com/fwlink/?LinkId=393693)」を参照してください。

## <a name="service-level-agreement"></a>サービス レベル契約

**Microsoft Online Services レベル アグリーメント:** 各サービスのサービス レベルを達成し、維持するというコミットメントに対して、財務上の支援を提供します。 サービス レベル 契約に記載されているように、各サービスのサービス レベルを達成および維持していない場合は、毎月のサービス料金の一部に対するクレジットの対象となる場合があります。 当社のサービスに関するサービス レベル契約の詳細については、「[Microsoft Online サービス レベル契約](https://go.microsoft.com/fwlink/?linkid=272026)」をダウンロードしてください。 システムの稼働時間、セキュリティ、プライバシー、コンプライアンスに関する情報の概要については、「[Office 365 による透明性のある運用](/office365/servicedescriptions/office-365-platform-service-description/service-health-and-continuity)」を参照してください。

**サービスの更新:** 更新とアップグレードは、地域、言語、データ センター、サブスクリプションなど、さまざまな要因に基づいて顧客にロールアウトされます。 したがって、既存のカスタマーが、すべてのアップデートやアップグレード機能を直ちに使用できるわけではありません。 リリースされたばかりの機能、またはリリースされる予定の機能については、 [Microsoft 365 ロードマップ](https://go.microsoft.com/fwlink/?LinkId=509914)を参照してください。 このトピックは、21Vianet によって操作されるOffice 365には適用されません。 サービス更新プログラムの詳細については、「[**21Vianet によって運用されるOffice 365の技術サポート、課金、サブスクリプション サポートの取得**](/microsoft-365/admin/contact-support-for-business-products)」を参照してください。

**対象となるリリース:** 対象リリースでは、組織または一連のユーザーが、標準リリース プロセスを開始する約 1 週間前に、選択したサービス更新プログラムのセットを受け取ります。 詳細については、 [Microsoft リリース オプションに関するページ](/office365/admin/manage/release-options-in-office-365)を参照してください。

**更新通知:** Microsoft は、サービスを正常に機能させるために管理者がアクションを実行する必要がある変更を事前に顧客に通知するよう努めています。 更新で管理者のアクションが必要となる場合、特に記載されていない限り、Microsoft では [Message Center](/office365/admin/manage/message-center) を介して少なくとも 30 日前に通知します。 ほとんどのサービス更新プログラムは、バグ修正、パフォーマンスの向上、およびセキュリティ更新プログラムであり、顧客に代わってゼロ アクションを必要とします。 新機能と改善された機能は、 [ビジネス ロードマップ用の Microsoft 365](https://roadmap.office.com/) にあります。 Microsoft は [、オンライン ライフサイクル ポリシー](https://support.microsoft.com/lifecycle#gp/osslpolicy)に従います。

---

**機能の可用性:** プラン間の機能の可用性を表示するには、[Microsoft 365 とプラットフォーム サービスの説明Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-platform-service-description)参照してください。
