---
title: Microsoft 365 のビジネスを管理する Windows 10 のドメインに参加しているデバイスを有効にします。
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: 保護するために Microsoft 365 を有効にする方法を学ぶ 10 の Windows デバイスがローカルの AD に参加しています。
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869148"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Microsoft 365 のビジネスを管理する Windows 10 のドメインに参加しているデバイスを有効にします。

組織は、Windows サーバーの Active Directory の設置型を使用している場合は、ローカルの認証を必要とする設置型のリソースへのアクセスを維持しながら、10 の Windows のデバイスを保護するために Microsoft 365 のビジネスを設定できます。Azure AD で 10 の Windows デバイスを登録して、Microsoft 365 のビジネスでのモバイル デバイス管理の登録に続いて、Azure Active directory、Active Directory を同期して設定することができます。
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Microsoft 365 のビジネスを管理するドメインに参加しているデバイスの設定します。

オンプレミスの Active Directory に加え、Azure Active Directory が提供する機能からメリットを享受するのには、組織のドメインに参加しているデバイスを設定するには、**ハイブリッド Azure AD には、デバイスが参加している**を実装できます。これらは、オンプレミスの Active Directory と、Azure Active Directory の両方に参加しているデバイスです。ハイブリッド Azure AD が参加しているデバイスの保護し、Microsoft 365 ビジネスによって管理されていることができます。 
  
ハイブリッド Azure の AD に参加して、Microsoft 365 ビジネスによって管理されている Windows 10 デバイスを作成するには、次の手順を完了します。
  
1. Azure Active Directory に、ユーザー、グループ、およびローカルの Active Directory から連絡先を同期するには、ディレクトリ同期ウィザードと Azure Active ディレクトリの説明に従って接続[Office 365 のディレクトリ同期の設定](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)を実行します。
    
    > [!NOTE]
    > 手順は、正確にマイクロソフト 365 ビジネスでも同じです。 
  
2. Azure AD に参加しているハイブリッドにする 10 の Windows のデバイスを有効にする 3 の手順を完了する前に、次の前提条件を満たしているかどうかを確認する必要があります。
    
   - Azure AD の最新バージョンを実行して接続します。
    
   - Azure AD 接続 Azure AD に参加しているハイブリッドにデバイスのすべてのコンピューター オブジェクトが同期します。コンピューター オブジェクトが特定の組織単位 (OU) に属しているし、これらの Ou は、Azure AD での同期に設定されているかどうかを確認する場合も同様に接続します。
    
3. 既存ドメインに参加している Windows の 10、デバイスのハイブリッド Azure AD 参加 Intune (Microsoft 365 ビジネス) でモバイル デバイス管理のためを登録を登録します。
    
4. [ハイブリッド Azure Active Directory が参加しているデバイスを構成する方法](https://go.microsoft.com/fwlink/p/?linkid=872870)のステップ バイ ステップの指示に従います。これは、オンプレミスの Active Directory の同期を有効にする 10 の Windows コンピューターを結合し、クラウドを可能にします。
    
5. モバイル デバイス管理のための 10 の Windows デバイスを登録するために、手順については[10 の Windows Intune グループ ポリシーを使用してデバイスの登録](https://go.microsoft.com/fwlink/p/?linkid=872871)を参照してください。ポリシーを設定して、グループでは、ローカル コンピューター レベルまたは一括操作では、ドメイン コント ローラー サーバーで、このグループ ポリシー設定を作成できます。 
    

