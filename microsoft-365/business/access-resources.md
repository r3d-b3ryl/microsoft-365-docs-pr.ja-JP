---
title: Microsoft 365 Business で Azure ADに参加しているデバイスからオンプレミスのリソースにアクセスする
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
description: Azure Active Directory に参加している Windows 10 デバイスから、業務アプリ、ファイル共有、プリンターなど、オンプレミスのリソースにアクセスする方法について説明します。
ms.openlocfilehash: 22edf0c23d6318e1f70bcb21b2cd697ea0a75da4
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688235"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a>Microsoft 365 Business Premium で Azure ADに参加しているデバイスからオンプレミスのリソースにアクセスする

この記事は、Microsoft 365 Business Premium に適用されます。

Azure Active Directory に参加しているすべての Windows 10 デバイスは、Microsoft 365 アプリなどのクラウドベースのすべてのリソースにアクセスし、Microsoft 365 Business Premium で保護できます。 また、業務 (LOB) アプリ、ファイル共有、プリンターなど、オンプレミスのリソースへのアクセスを許可することもできます。 アクセスを許可するには [、Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) を使用して、オンプレミスの Active Directory と Azure Active Directory を同期します。 

詳細については、「Azure Active Directory でのデバイス [管理の概要」を参照してください](https://docs.microsoft.com/azure/active-directory/device-management-introduction)。
手順の概要については、次のセクションでも説明します。
 
## <a name="run-azure-ad-connect"></a>Azure AD Connect を実行する

次の手順を実行して、組織の Azure ADに参加しているデバイスがオンプレミスのリソースにアクセスできます。
  
1. ローカル Active Directory から Azure Active Directory にユーザー、グループ、連絡先を同期するには、「Office [365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)のディレクトリ同期をセットアップする」の説明に従って、ディレクトリ同期ウィザードと Azure AD Connect を実行します。
    
2. ディレクトリ同期が完了したら、組織の Windows 10 デバイスが Azure に参加ADします。 この手順は、各 Windows 10 デバイスで個別に実行します。 詳細 [については、「Microsoft 365 Business Premium](set-up-windows-devices.md) ユーザー向け Windows デバイスのセットアップ」を参照してください。 
    
3. Windows 10 デバイスが Azure ADに参加したら、各ユーザーはデバイスを再起動し、Microsoft 365 Business Premium の資格情報でサインインする必要があります。 すべてのデバイスは、オンプレミスのリソースにもアクセスできます。
    
Azure または参加しているデバイスのオンプレミス リソースにアクセスするために、追加AD必要はありません。 この機能は、Windows 10 に組み込組み込みです。 

パスワード以外の AADJ デバイスへのログインを計画している場合は、WHFB 資格情報ログインを使用して PIN/生体測定法のようにして、オンプレミスのリソース (共有、プリンターなど) にアクセスします。など) に従います。 https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base
  
上記の Azure AD 参加デバイス構成に展開する準備ができていない場合は、ハイブリッド Azure AD 参加デバイス構成の設定 [を検討してください](manage-windows-devices.md)。
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Windows デバイスを Azure デバイスに参加AD

Azure-ADに参加した Windows デバイスが以前にドメインに参加しているか、ワークグループに参加している場合は、次の制限事項を考慮してください。
  
- デバイス Azure AD参加すると、既存のプロファイルを参照せずに新しいユーザーが作成されます。 プロファイルは手動で移行する必要があります。 ユーザー プロファイルには、お気に入り、ローカル ファイル、ブラウザーの設定、スタート メニューの設定など、情報が含まれている。 最善の方法は、既存のファイルと設定を新しいプロファイルにマップするサード パーティ製ツールを見つけ出す方法です。

- デバイスがグループ ポリシー オブジェクト (GPO) を使用している場合、一部の GPO では Intune で同等の [構成](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) サービス プロバイダー (CSP) を使用できない場合があります。 [MMAT ツールを実行して、](https://www.microsoft.com/download/details.aspx?id=45520)既存の GPO に対応する CSP を検索します。

- ユーザーは、Active Directory 認証に依存するアプリケーションに対して認証を行う必要があります。 レガシ アプリを評価し、可能であれば最新の認証を使用するアプリへの更新を検討します。

- Active Directory プリンターの検出が機能しません。 すべてのユーザーにプリンターの直接パスを指定するか、ユニバーサル印刷 [を使用できます](https://aka.ms/UPDocs)。
