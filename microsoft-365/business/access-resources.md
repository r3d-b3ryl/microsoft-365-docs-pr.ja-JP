---
title: Microsoft 365 Business で Azure AD に参加しているデバイスからオンプレミスのリソースにアクセスする
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
description: Azure Active Directory に参加している Windows 10 デバイスから、基幹業務アプリケーション、ファイル共有、プリンターなどのオンプレミスのリソースにアクセスする方法について説明します。
ms.openlocfilehash: 2144268f5cbab67c39d5902622c61c0c35e6481c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295312"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Microsoft 365 Business Premium の Azure AD に参加しているデバイスからオンプレミスのリソースにアクセスする

この記事は、Microsoft 365 Business Premium に適用されます。

Azure Active Directory に参加している Windows 10 デバイスはすべて、Microsoft 365 アプリなどのクラウドベースのすべてのリソースにアクセスでき、Microsoft 365 Business Premium で保護することができます。 基幹業務 (LOB) アプリ、ファイル共有、プリンターなどの社内リソースへのアクセスを許可することもできます。 アクセスを許可するには、 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) を使用してオンプレミスの active Directory を Azure active directory と同期します。 

詳細については、「 [Azure Active Directory でのデバイス管理の概要](https://docs.microsoft.com/azure/active-directory/device-management-introduction)」を参照してください。
手順の概要についても、以下のセクションで説明します。
 
## <a name="run-azure-ad-connect"></a>Azure AD Connect を実行する

次の手順を実行して、組織の Azure AD に参加しているデバイスがオンプレミスのリソースにアクセスできるようにします。
  
1. ユーザー、グループ、および連絡先をローカルの Active Directory から Azure Active Directory に同期するには、「 [Set up Directory synchronization For Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)」の説明に従って、ディレクトリ同期ウィザードと Azure AD Connect を実行します。
    
2. ディレクトリ同期が完了したら、組織の Windows 10 デバイスが Azure AD に参加していることを確認します。 この手順は、各 Windows 10 デバイスで個別に実行します。 詳細については、「 [Microsoft 365 Business Premium ユーザーの Windows デバイスをセットアップする](set-up-windows-devices.md) 」を参照してください。 
    
3. Windows 10 デバイスが Azure AD に参加している場合、各ユーザーはデバイスを再起動して、Microsoft 365 Business Premium の資格情報でサインインする必要があります。 これで、すべてのデバイスがオンプレミスのリソースにもアクセスできるようになりました。
    
Azure AD に参加しているデバイスのオンプレミスのリソースにアクセスするために、追加の手順は必要ありません。 この機能は、Windows 10 に組み込まれています。 

[PIN/Bio] のように、パスワード以外の方法で、(WHFB credential ログイン経由で) AADJ デバイスにログインし、オンプレミスのリソース (共有、プリンター) にアクセスする予定がある場合。など)。 https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
前述の Azure AD に参加しているデバイス構成に組織が展開する準備ができていない場合は、 [ハイブリッド AZURE ad の参加](manage-windows-devices.md)しているデバイス構成を設定することを検討してください。
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Windows デバイスを Azure AD に参加させる際の考慮事項

Azure AD に参加している Windows デバイスが以前にドメインに参加しているか、ワークグループに参加していた場合は、次の制限事項を考慮してください。
  
- デバイス Azure AD が参加すると、既存のプロファイルを参照せずに新しいユーザーが作成されます。 プロファイルは手動で移行する必要があります。 ユーザープロファイルには、お気に入り、ローカルファイル、ブラウザーの設定、および [スタート] メニューの設定などの情報が含まれています。 最善の方法は、既存のファイルと設定を新しいプロファイルにマップするためのサードパーティ製ツールを検索することです。

- デバイスがグループポリシーオブジェクト (GPO) を使用している場合、一部の Gpo には Intune での同等の [構成サービスプロバイダー](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) が含まれていないことがあります。 [Mmat ツール](https://www.microsoft.com/download/details.aspx?id=45520)を実行して、既存の gpo の同等の csp を検索します。

- ユーザーは、Active Directory 認証に依存するアプリケーションに対して認証を行うことができません。 レガシアプリを評価し、可能であればモダン認証を使用するアプリに更新することを検討します。

- Active Directory プリンターの検出は機能しません。 すべてのユーザーに直接のプリンターパスを提供したり、 [ハイブリッドクラウド印刷](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)を使用したりすることができます。
