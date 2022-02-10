---
title: Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する
description: 認証を提供するために、Azure ADと通信するための重要なAD手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 3db3d469f7b417035e6ae11507c54c6bad871a89
ms.sourcegitcommit: cafca45069819a44c7cf8c67f6c1e105de1b3393
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/10/2022
ms.locfileid: "62520393"
---
# <a name="prepare-on-premises-resources-access-for-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップ用にオンプレミス リソースアクセスを準備する

Microsoft Managed Desktop では、デバイスは自動的にデバイスに参加Azure Active Directory (Azure AD)。 このため、オンプレミスの Active Directory を使用している場合は、オンプレミスの Active Directory に参加Azure ADデバイスがオンプレミスの Active Directory と通信できる必要があります。

> [!NOTE]  
> *ハイブリッド* Azure AD参加は、Microsoft Managed Desktop ではサポートされていません。

Azure Active Directoryユーザーがシングル モード (SSO) Sign-On活用できます。 シングル サインオンとは、通常、リソースを使用する度に資格情報を提供する必要が生じないという意味です。

参加方法の詳細Azure Active Directory、「[How to: Plan your Azure AD参加実装」を参照してください](/azure/active-directory/devices/azureadjoin-plan)。 Azure AD に参加しているデバイスでのシングル Sign-On (SSO) のバックグラウンド情報については、「参加しているデバイスでの SSO to オンプレミス リソースの動作Azure AD[参照してください](/azure/active-directory/devices/azuread-join-sso#how-it-works)。

この記事では、ローカルの Active Directory 接続に依存するアプリや他のリソースが Microsoft Managed Desktop でスムーズに動作するために確認する必要がある内容について説明します。

## <a name="single-sign-on-for-on-premises-resources"></a>オンプレミス Sign-Onの単一のリソース

UPN Sign-Onを使用したシングル デバイス (SSO) は、Microsoft 管理デスクトップ デバイスで既定で有効になっています。 ただし、ユーザーはビジネス向けWindows Helloを使用できますが、追加のセットアップ手順が必要です。

### <a name="single-sign-on-by-using-upn-and-password"></a>UPN Sign-Onパスワードを使用した単一のデバイス

ほとんどの組織では、ユーザーは MICROSOFT 管理デスクトップ デバイスで SSO を使用して UPN とパスワードによる認証を行えます。 この関数が動作する場合は、次の機能を確認してください。

- ユーザーがAzure AD Connectを確認します。 サーバー 2008 R2 以降で実行されているオンプレミスの Active Directory Windows使用する必要があります。
- サポートされているAzure AD Connectを実行している必要があります。 次の 3 つの属性を次の属性と同期Azure AD。
    - DNS ドメイン Active Directory (ユーザーが存在する場所) の名前を指定します。
    - オンプレミスの Active Directory の NetBIOS (ユーザーが存在する場所)。
    - ユーザーの SAM アカウント名。

### <a name="single-sign-on-by-using-windows-hello-for-business"></a>ビジネスSign-Onを使用した単一Windows Helloサービス

Microsoft Managed Desktop デバイスは、ビジネス向けアプリを使用することで、ユーザーにパスワードを使用Windows Hello提供します。 Windows Hello for Business が、ユーザーがそれぞれの UPN とパスワードを指定せずに動作するには、「Windows Hello for Business を使用してオンプレミス [Azure AD Single-Sign](/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base) に参加しているデバイスを構成する」を参照し、要件を確認してから、そこに示す手順に従います。

## <a name="apps-and-resources-that-use-authentication"></a>認証を使用するアプリとリソース

詳細については[、「Azure コンテンツ セット内](/azure/active-directory/devices/azureadjoin-plan#understand-considerations-for-applications-and-resources)のアプリケーションとリソースに関する考慮事項を理解する」を参照して、アプリを使用して動作するようにアプリを設定Azure Active Directory。 まとめると、以下のようになります。

| アプリまたはサービス | タスク |
| ------ | ------ |
| クラウドベースのアプリ | Azure AD アプリ ギャラリーに追加されたアプリなど、クラウドベースのアプリを使用する場合、Microsoft Managed Desktop を操作するためにそれ以上の準備を必要としません。 ただし、Web アカウント マネージャー (WAM) を使用しない Win32 アプリでは、ユーザーに認証を求めるメッセージが表示される場合があります。 |
| オンプレミスでホストされるアプリ | オンプレミスでホスト **されているアプリの場合は**、必ずそれらのアプリをブラウザーの信頼済みサイトリストに追加してください。 この手順では、ユーザー Windows求めることなく、認証をシームレスに動作できます。 アプリを追加するには、「構成可能な設定 [」リファレンスの](../working-with-managed-desktop/config-setting-ref.md#trusted-sites) 「信頼できる [サイト」を参照してください](../working-with-managed-desktop/config-setting-ref.md)。 |
| Active Directory フェデレーション サービス | Active Directory フェデレーション サービスを使用している場合は、「シングル サインオンを FS で確認して管理する」の手順を使用して SSO が有効AD [します](/previous-versions/azure/azure-services/jj151809(v=azure.100))。 |
| 古いプロトコルを使用するオンプレミス アプリ | オンプレミス **で古い** プロトコルを使用するアプリの場合、デバイスが認証のためにオンプレミスのドメイン コントローラーにアクセスできる限り、追加のセットアップは必要ありません。 ただし、これらのアプリケーションにセキュリティで保護されたアクセスを提供するには、アプリケーション プロキシAzure AD展開する必要があります。 詳細については、「アプリケーション プロキシを介したオンプレミス アプリケーションへのリモート アクセス[Azure Active Directory参照してください](/azure/active-directory/manage-apps/application-proxy)。 |
| コンピューター認証を使用したオンプレミス アプリ | オンプレミスで **実行され、** コンピューター認証に依存するアプリはサポートされていないので、新しいバージョンへの置き換えも検討する必要があります。 |

### <a name="network-shares-that-use-authentication"></a>認証を使用するネットワーク共有

UNC パスを使用してデバイスがオンプレミスのドメイン コントローラーにアクセスできる限り、ユーザーがネットワーク共有にアクセスするには、追加のセットアップは必要ありません。

### <a name="printers"></a>プリンター

ハイブリッド クラウド印刷を構成しない限り、Microsoft Managed Desktop デバイスは、オンプレミスの Active Directory に発行されたプリンター [に接続できません](/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)。

クラウド専用環境ではプリンターを自動的に検出することはできませんが、ユーザーは、デバイスがオンプレミスのドメイン コントローラーにアクセスできる限り、プリンター パスまたはプリンター キュー パスを使用してオンプレミス プリンターを使用できます。

<!--add fuller material on printers when available-->
## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>Microsoft Managed Desktop の準備をする手順

1. [Microsoft マネージド デスクトップの前提条件](prerequisites.md)を確認します。
1. [準備状況の評価ツール](readiness-assessment-tool.md)を実行します。
1. [ポータル サイト](../get-started/company-portal.md)を購入します。
1. [ゲスト アカウントの前提条件](guest-accounts.md)を確認します。
1. [ネットワーク構成](network.md)をチェックします。
1. [証明書とネットワーク プロファイル](certs-wifi-lan.md)を準備します。
1. データへのユーザー アクセスを準備します (この記事)。
1. [アプリを準備します](apps.md)。
1. [マップ済みドライブを準備します](mapped-drives.md)。
1. [印刷リソースを準備します](printing.md)。
1. [デバイス名](address-device-names.md)をアドレス指定します。
