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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Azure Active Directory に参加している Windows 10 デバイスから、基幹業務アプリケーション、ファイル共有、プリンターなどのオンプレミスのリソースにアクセスする方法について説明します。
ms.openlocfilehash: ab9049e78617372463b8446dc8f8bc0089d8c117
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981663"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>Microsoft 365 Business で Azure AD に参加しているデバイスからオンプレミスのリソースにアクセスする

Azure Active Directory に参加している Windows 10 デバイスはすべて、Office 365 アプリなどのクラウドベースのすべてのリソースへのアクセス権を持ち、Microsoft 365 Business で保護することができます。 基幹業務 (LOB) アプリ、ファイル共有、およびプリンターなどのオンプレミスのリソースへのアクセスも許可するには、 [AZURE AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)を使用して、オンプレミスの active Directory を Azure active directory と同期する必要があります。 次のビデオでは、最も一般的なシナリオに対してこの設定を行う手順を詳しく説明します。
 
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]

詳細については、「 [Azure Active Directory でのデバイス管理の概要](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction)」を参照してください。
手順の概要についても、以下のセクションで説明します。

## <a name="run-azure-ad-connect"></a>Azure AD Connect を実行する

次の手順を実行して、組織の Azure AD に参加しているデバイスがオンプレミスのリソースにアクセスできるようにします。
  
1. ユーザー、グループ、および連絡先をローカルの Active Directory から Azure Active Directory に同期するには、「 [Office 365 のディレクトリ同期のセットアップ](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)」の説明に従って、ディレクトリ同期ウィザードと Azure AD Connect を実行します。
    
2. ディレクトリ同期が完了したら、組織の Windows 10 デバイスが Azure AD に参加していることを確認します。 この手順は、各 Windows 10 デバイスで個別に実行します。 詳細については、「 [Microsoft 365 Business ユーザーの Windows デバイスをセットアップする](set-up-windows-devices.md)」を参照してください。 
    
3. Windows 10 デバイスが Azure AD に参加している場合、各ユーザーはデバイスを再起動し、Microsoft 365 Business 資格情報を使用してログインする必要があります。 これで、すべてのデバイスがオンプレミスのリソースにもアクセスできるようになります。
    
Azure AD に参加しているデバイスのオンプレミスのリソースにアクセスするために、追加の手順は必要ありません。 これは、Windows 10 で使用可能な組み込みの機能です。 
  
前述の Azure AD に参加しているデバイス構成に組織が展開する準備ができていない場合は、[ハイブリッド AZURE ad の参加](manage-windows-devices.md)しているデバイス構成を設定することを検討してください。
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Windows デバイスを Azure AD に参加させる際の考慮事項

以前にドメインに参加していた、またはワークグループ内にある Windows デバイスに Azure AD が参加している場合は、次の制限事項を考慮する必要があります。
  
- デバイス Azure AD が参加すると、既存のプロファイルを参照せずに新しいユーザーが作成されます。 この問題を解決するには、プロファイルを手動で移行する必要があります。 ユーザープロファイルには、お気に入り、ローカルファイル、ブラウザーの設定、スタートメニューの設定などの情報が含まれています。最善の方法は、既存のファイルと設定を新しいプロファイルにマップするためのサードパーティ製ツールを見つけることです。

- デバイスがグループポリシーオブジェクト (GPO) を使用している場合、一部の Gpo には Intune での同等の[構成サービスプロバイダー](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) が含まれていないことがあります。 [Mmat ツール](https://www.microsoft.com/download/details.aspx?id=45520)を実行して、既存の gpo の同等の csp を検索します。

- ユーザーは、Active Directory 認証に依存するアプリケーションに対して認証を行うことができなくなります。 これに対処するには、レガシアプリを使用して評価し、可能であればモダン認証を使用するアプリに更新することを検討します。

- Active Directory プリンターの検出は機能しません。 この問題を解決するには、すべてのユーザーの直接プリンターパスを提供するか、[ハイブリッドクラウド印刷](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)を利用します。
