---
title: アクセスは、オンプレミス マイクロソフト 365 ビジネスで Azure AD に参加しているデバイスからのリソース
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: 基幹業務アプリケーション、ファイル共有、および Azure Active Directory からプリンターに Windows の 10 のデバイスが参加しているように、オンプレミスのリソースへのアクセスを取得する方法について説明します。
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869026"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a>アクセスは、オンプレミス マイクロソフト 365 ビジネスで Azure AD に参加しているデバイスからのリソース

Azure Active directory が参加しているすべての Windows 10 デバイスは Office 365 アプリケーションなどのすべてのクラウド ベースのリソースへのアクセスがあり、Microsoft 365 のビジネスを保護します。基幹業務 (LOB) アプリケーション、ファイル共有、およびプリンターのように、オンプレミスのリソースへのアクセス許可、 [Azure AD 接続](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect)を使用して、Azure Active Directory で、オンプレミスの Active Directory を同期する必要があります。[Azure Active Directory 内のデバイスの管理の概要](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction)の詳細についてを参照してください。 
  
## <a name="run-azure-ad-connect"></a>実行 Azure AD 接続します。

設置型のリソースにアクセスするための組織の Azure AD が参加しているデバイスを有効にするのには、次の手順を完了します。
  
1. Azure Active Directory に、ユーザー、グループ、およびローカルの Active Directory から連絡先を同期するには、ディレクトリの同期ウィザードを実行して、Azure AD 接続は、 [Office 365 のディレクトリ同期の設定](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)で説明されています。
    
2. ディレクトリ同期処理が完了したら、組織の Windows 10 のデバイスは、Azure AD が参加していることを確認します。この手順は、Windows 10 デバイスごとに個別に行われます。詳細については[Microsoft 365 ビジネス ユーザー向けの Windows デバイスの設定](set-up-windows-devices.md)を参照してください。 
    
3. 10 の Windows のデバイスには、Azure AD が参加しているが、各ユーザーは、デバイスと Microsoft 365 ビジネス資格情報でログイン再起動します。すべてのデバイスも、オンプレミスのリソースへのアクセスがされます。
    
追加の手順は、オンプレミス AD の Azure のリソースには、デバイスが参加しているへのアクセスを取得するために必要ではありません。これは、10 の Windows で使用できる組み込みの機能です。 
  
組織が構成では、Azure AD 参加しているデバイス上で説明した展開する準備がない場合は、[ハイブリッド Azure AD 参加済みのデバイス構成](manage-windows-devices.md)の設定を検討してください。
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a>Azure AD に、Windows のデバイスを結合する際の考慮事項

Azure AD のドメインに参加されていた Windows デバイスを結合する場合、またはワークグループでは、次の制限事項を考慮する必要があります。
  
- デバイス Azure AD に参加する場合は、既存のプロファイルを参照することがなく新しいユーザーを作成します。これを修正するには、プロファイルを手動で移行する必要があります。ユーザー プロファイルには、[お気に入り]、[ローカル ファイル、ブラウザーの設定、[スタート] メニューの設定などのような情報が含まれています。最善のアプローチは、既存のファイルおよび設定を新しいプロファイルにマップするサードパーティ製のツールを見つけること
    
- デバイスがグループ ポリシー オブジェクト (GPO) を使用しているいくつかの Gpo 必要はありません同等[構成サービス プロバイダー](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) Intune で。[MMAT ツール](https://www.microsoft.com/download/details.aspx?id=45520)に匹敵する Csp を既存の Gpo の検索を実行します。 
    
- ユーザーは Active Directory 認証に依存するアプリケーションを認証することができません。対処するためこのレガシ アプリケーションを使用して評価し、可能な場合は最新の認証を使用するアプリケーションへの更新を検討してください。
    
- アクティブ ディレクトリのプリンターの検出は行われません。これを修正するには、直接プリンターのパスを提供するすべてのユーザーまたは[ハイブリッド クラウド印刷](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)を活用します。
    

