---
title: Microsoft マネージドデスクトップへのオンプレミスリソースアクセスの準備
description: Azure ad が認証を提供するためにオンプレミスの ad と通信できることを確認するための重要な手順
keywords: microsoft マネージドデスクトップ、microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 2317a0581b356dadbde2042920ed2542f0e2203c
ms.sourcegitcommit: 392b906e64d27366b47931e8285b625e5e2f884e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2019
ms.locfileid: "31838168"
---
#  <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Microsoft マネージドデスクトップへのオンプレミスリソースアクセスの準備

Microsoft マネージドデスクトップでは、デバイスは自動的に Azure Active Directory に参加します。 これは、オンプレミスの active directory を使用している場合に、Azure AD に参加しているデバイスがオンプレミスの active directory と通信できることを確認するために、いくつかのことを確認する必要があることを意味します。 

> [!NOTE]  
> *ハイブリッド*Azure AD join は、Microsoft マネージドデスクトップではサポートされていません。

Azure Active Directory では、ユーザーはシングルサインオン (SSO) を利用できます。これは、通常、リソースを使用するたびに資格情報を提供する必要がないことを意味します。

azure Active Directory への参加の詳細については、「 [How to: Plan for azure AD join implementation](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)」を参照してください。 azure ad に参加しているデバイスのシングルサインオン (sso) に関する背景情報については、「azure ad に参加している[デバイスでの sso とオンプレミスのリソースのしくみ](https://docs.microsoft.com/azure/active-directory/devices/azuread-join-sso#how-it-works)」を参照してください。


このトピックでは、ローカルの Active Directory 接続に依存するアプリとその他のリソースが、Microsoft マネージドデスクトップで円滑に動作するようにするために確認する必要がある事柄について説明します。


## <a name="single-sign-on-for-on-premises-resources"></a>オンプレミスのリソースのシングルサインオン

UPN とパスワードを使用したシングルサインオン (SSO) は、Microsoft マネージドデスクトップデバイスでは既定で有効になっています。 ただし、ユーザーは Windows Hello for business を使用することもできます。これには、いくつかのセットアップ手順が必要になります。 

### <a name="single-sign-on-by-using-upn-and-passwords"></a>UPN とパスワードを使用したシングルサインオン

ほとんどの組織では、ユーザーは SSO を使用して、Microsoft マネージドデスクトップデバイス上の UPN とパスワードによる認証を行うことができます。 ただし、これが正常に動作することを確認するには、次の点を再度確認する必要があります。

- Azure active directory (AAD) Connect がセットアップされており、Windows server 2008 R2 以降を実行しているオンプレミスの Active directory サーバーを使用していることを確認します。
- AAD Connect でサポートされているバージョンが実行されており、次の3つの属性を Azure AD と同期するように設定されていることを確認します。 
    - オンプレミスの Active Directory の DNS ドメイン名 (エンドユーザーが配置されている場所)
    - yor オンプレミスの Active Directory の NetBIOS (エンドユーザーが配置されている場所)
    - ユーザーの SAM アカウント名


### <a name="single-sign-on-by-using-windows-hello-for-business"></a>Windows Hello for business を使用したシングルサインオン

Microsoft マネージドデスクトップデバイスでは、Windows Hello for business を使用することで、ユーザーにすばやくパスワードを提供することがなくなります。 ユーザーが UPN とパスワードを入力しなくても windows hello for business が機能するようにするには、「 [windows hello for business を使用して Azure AD に参加しているデバイスを構成](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base)する」を参照して、要件を確認し、次の手順を実行します。手順について説明します。


## <a name="apps-and-resources-that-use-authentication"></a>認証を使用するアプリとリソース

azure Active Directory と連携するようにアプリをセットアップするための詳細なガイダンスについては、「azure コンテンツセットの[アプリケーションとリソースに関する考慮事項](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources)」を参照してください。 概要:


- Azure AD app gallery に追加されたものなど、**クラウドベースのアプリ**を使用している場合、多くの場合、Microsoft マネージドデスクトップを操作するための準備は必要ありません。 ただし、Web アカウントマネージャー (WAM) を使用していない Win32 アプリでも、ユーザーに対して認証を求めるメッセージが表示されることがあります。

- **オンプレミスでホスト**されているアプリの場合は、それらのアプリをブラウザーの信頼済みサイトの一覧に追加してください。 これにより、ユーザーが資格情報の入力を求められることなく、Windows 認証がシームレスに動作するようになります。 これを行うには、[構成可能な設定のリファレンス](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref)で、[[信頼済みサイト](https://docs.microsoft.com/microsoft-365/managed-desktop/working-with-managed-desktop/config-setting-ref#trusted-sites)] を参照してください。

- Active Directory フェデレーションサービスを使用している場合は、「AD FS を使用して[シングルサインオンを確認および管理](https://docs.microsoft.com/previous-versions/azure/azure-services/jj151809(v=azure.100))する」の手順を使用して、SSO が有効になっていることを確認します。 

- **オンプレミス**のアプリで古いプロトコルを使用する場合、デバイスが認証のためにオンプレミスのドメインコントローラーにアクセスできる限り、特別なセットアップは不要です。 ただし、これらのアプリケーションにセキュリティで保護されたアクセスを提供するには、Azure AD アプリケーションプロキシを展開する必要があります。 詳細については、「 [Azure Active Directory のアプリケーションプロキシを使用したオンプレミスアプリケーションへのリモートアクセス](https://docs.microsoft.com/azure/active-directory/manage-apps/application-proxy)」を参照してください。

- オンプレミスで実行され、**コンピューター認証に依存**するアプリはサポートされていないため、これらを新しいバージョンに置き換えることを検討する必要があります。

### <a name="network-shares-that-use-authentication"></a>認証を使用するネットワーク共有

デバイスが UNC パスを使用してオンプレミスのドメインコントローラーにアクセスできる限り、ユーザーがネットワーク共有にアクセスするための特別なセットアップは必要ありません。

### <a name="printers"></a>プリンター

Microsoft マネージドデスクトップデバイスは、[ハイブリッドクラウド印刷](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)を構成していない限り、オンプレミスの Active Directory に公開されているプリンターに接続することはできません。

プリンターをクラウドのみの環境で自動的に検出することはできませんが、デバイスがオンプレミスのドメインコントローラーにアクセスできる限り、ユーザーはプリンターのパスまたはプリンターキューのパスを使用してオンプレミスのプリンターを使用できます。

<!--add fuller material on printers when available-->