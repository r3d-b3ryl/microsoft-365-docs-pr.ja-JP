---
title: Microsoft 365 Business で Azure AD に参加しているデバイスからオンプレミスのリソースにアクセスする
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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Azure Active Directory に参加している Windows 10 デバイスから、基幹業務アプリケーション、ファイル共有、プリンターなどのオンプレミスのリソースにアクセスする方法について説明します。
ms.openlocfilehash: fdc1eca6913ba6af4f6b65691fdee2165e7c827e
ms.sourcegitcommit: 8193b7da5b1a415835d02ca96883c351df7326ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/14/2019
ms.locfileid: "38323397"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Microsoft 365 Business で Azure AD に参加しているデバイスからオンプレミスのリソースにアクセスする

Azure Active Directory に参加している Windows 10 デバイスはすべて、Office 365 アプリなどのクラウドベースのすべてのリソースにアクセスでき、Microsoft 365 Business で保護することができます。 基幹業務 (LOB) アプリ、ファイル共有、プリンターなどの社内リソースへのアクセスを許可することもできます。 アクセスを許可するには、 [AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)を使用してオンプレミスの active Directory を Azure active directory と同期します。 

詳細については、「 [Azure Active Directory でのデバイス管理の概要](https://docs.microsoft.com/azure/active-directory/device-management-introduction)」を参照してください。
手順の概要についても、以下のセクションで説明します。

## <a name="run-azure-ad-connect"></a>Azure AD Connect を実行する

次の手順を実行して、組織の Azure AD に参加しているデバイスがオンプレミスのリソースにアクセスできるようにします。
  
1. ユーザー、グループ、および連絡先をローカルの Active Directory から Azure Active Directory に同期するには、「 [Set up Directory synchronization For Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)」の説明に従って、ディレクトリ同期ウィザードと Azure AD Connect を実行します。
    
2. ディレクトリ同期が完了したら、組織の Windows 10 デバイスが Azure AD に参加していることを確認します。 この手順は、各 Windows 10 デバイスで個別に実行します。 詳細については、「 [Microsoft 365 Business ユーザーの Windows デバイスをセットアップする](set-up-windows-devices.md)」を参照してください。 
    
3. Windows 10 デバイスが Azure AD に参加している場合、各ユーザーはデバイスを再起動し、Microsoft 365 Business 資格情報を使用してサインインする必要があります。 これで、すべてのデバイスがオンプレミスのリソースにもアクセスできるようになりました。
    
Azure AD に参加しているデバイスのオンプレミスのリソースにアクセスするために、追加の手順は必要ありません。 この機能は、Windows 10 に組み込まれています。 
  
前述の Azure AD に参加しているデバイス構成に組織が展開する準備ができていない場合は、[ハイブリッド AZURE ad の参加](manage-windows-devices.md)しているデバイス構成を設定することを検討してください。
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a>Windows デバイスを Azure AD に参加させる際の考慮事項

Azure AD に参加している Windows デバイスが以前にドメインに参加しているか、ワークグループに参加していた場合は、次の制限事項を考慮してください。
  
- デバイス Azure AD が参加すると、既存のプロファイルを参照せずに新しいユーザーが作成されます。 プロファイルは手動で移行する必要があります。 ユーザープロファイルには、お気に入り、ローカルファイル、ブラウザーの設定、および [スタート] メニューの設定などの情報が含まれています。 最善の方法は、既存のファイルと設定を新しいプロファイルにマップするためのサードパーティ製ツールを検索することです。

- デバイスがグループポリシーオブジェクト (GPO) を使用している場合、一部の Gpo には Intune での同等の[構成サービスプロバイダー](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) が含まれていないことがあります。 [Mmat ツール](https://www.microsoft.com/download/details.aspx?id=45520)を実行して、既存の gpo の同等の csp を検索します。

- ユーザーは、Active Directory 認証に依存するアプリケーションに対して認証を行うことができません。 レガシアプリを評価し、可能であればモダン認証を使用するアプリに更新することを検討します。

- Active Directory プリンターの検出は機能しません。 すべてのユーザーに直接のプリンターパスを提供したり、[ハイブリッドクラウド印刷](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)を使用したりすることができます。
