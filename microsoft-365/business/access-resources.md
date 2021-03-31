---
title: Microsoft 365 Business の Azure AD参加デバイスからオンプレミス リソースにアクセスする
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Azure Active Directory に参加している Windows 10 デバイスから、一行のビジネス アプリ、ファイル共有、プリンターなど、オンプレミスのリソースにアクセスする方法について説明します。
ms.openlocfilehash: 1bca0beb3ccc78e670ad33ce446b9b3f7c372ba7
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445350"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Microsoft 365 Business Premium の Azure AD参加デバイスからオンプレミス リソースにアクセスする

この記事は、Microsoft 365 Business Premium に適用されます。

Azure Active Directory に参加している Windows 10 デバイスは、Microsoft 365 アプリなど、すべてのクラウドベースのリソースにアクセスできます。Microsoft 365 Business Premium によって保護できます。 また、業務 (LOB) アプリ、ファイル共有、プリンターなど、オンプレミスのリソースへのアクセスを許可することもできます。 アクセスを許可するには [、Azure AD接続](/azure/active-directory/connect/active-directory-aadconnect) を使用して、オンプレミスの Active Directory と Azure Active Directory を同期します。 

詳細については [、「Azure Active Directory でのデバイス管理の概要」を参照してください](/azure/active-directory/device-management-introduction)。
手順は、次のセクションでも要約されています。
 
## <a name="run-azure-ad-connect"></a>Azure AD接続を実行する

以下の手順を実行して、組織の Azure ADに参加しているデバイスがオンプレミス のリソースにアクセスできます。
  
1. ローカル Active Directory から Azure Active Directory にユーザー、グループ、連絡先を同期するには、「Office [365](../enterprise/set-up-directory-synchronization.md)のディレクトリ同期のセットアップ」の説明に従って、ディレクトリ同期ウィザードと Azure AD Connect を実行します。
    
2. ディレクトリ同期が完了したら、組織の Windows 10 デバイスが Azure デバイスADしてください。 この手順は、各 Windows 10 デバイスで個別に実行されます。 詳細 [については、「Microsoft 365 Business Premium](set-up-windows-devices.md) ユーザー向け Windows デバイスのセットアップ」を参照してください。 
    
3. Windows 10 デバイスが Azure AD参加したら、各ユーザーはデバイスを再起動し、Microsoft 365 Business Premium 資格情報でサインインする必要があります。 これで、すべてのデバイスがオンプレミスのリソースにもアクセスできます。
    
Azure に参加しているデバイスのオンプレミス リソースにアクセスするには、追加AD必要ありません。 この機能は Windows 10 に組み込まれる。 

パスワード以外の AADJ デバイスにログインする計画がある場合 WHFB 資格情報ログインを介して PIN/Bio-metric のようにし、オンプレミスのリソース (共有、プリンター.) にアクセスします。など)、フォローしてください https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
組織が上記の Azure AD参加デバイス構成に展開する準備ができていない場合は、ハイブリッド Azure AD [参加デバイス構成のセットアップを検討してください](manage-windows-devices.md)。
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Windows デバイスを Azure デバイスに参加する場合の考慮事項AD

Azure-AD参加した Windows デバイスが以前にドメインに参加しているか、ワークグループに参加している場合は、次の制限事項を考慮してください。
  
- デバイス Azure が参加AD、既存のプロファイルを参照せずに新しいユーザーを作成します。 プロファイルは手動で移行する必要があります。 ユーザー プロファイルには、お気に入り、ローカル ファイル、ブラウザー設定、スタート メニュー設定のような情報が含まれる。 最適な方法は、既存のファイルと設定を新しいプロファイルにマップするサード パーティ製のツールを見つける方法です。

- デバイスがグループ ポリシー オブジェクト (GPO) を使用している場合、一部の GPO には Intune で同等の [構成](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) サービス プロバイダー (CSP) が含されていない場合があります。 [MMAT ツールを実行して](https://www.microsoft.com/download/details.aspx?id=45520)、既存の GPO に対応する CSP を検索します。

- ユーザーが Active Directory 認証に依存するアプリケーションに対して認証できない場合があります。 従来のアプリを評価し、可能であれば最新の Auth を使用するアプリへの更新を検討します。

- Active Directory プリンターの検出が機能しません。 すべてのユーザーに直接プリンター パスを指定するか、ユニバーサル 印刷 [を使用できます](/universal-print/)。

### <a name="related-articles"></a>関連記事

[Azure AD Connect の前提条件](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites)
