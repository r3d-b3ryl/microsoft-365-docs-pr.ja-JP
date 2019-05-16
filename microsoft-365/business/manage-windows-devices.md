---
title: Microsoft 365 Business で管理されるドメインに参加している Windows 10 デバイスを有効にする
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Microsoft 365 を有効にして、ローカルの AD に参加している Windows 10 デバイスを保護する方法について説明します。
ms.openlocfilehash: af0e78ef6e79bfd612b11a16538e7afcd377ffb0
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071552"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Microsoft 365 Business で管理されるドメインに参加している Windows 10 デバイスを有効にする

組織がオンプレミスの Windows Server Active Directory を使用している場合は、Windows 10 のデバイスを保護するように Microsoft 365 Business をセットアップし、ローカル認証を必要とするオンプレミスのリソースへのアクセスを維持することができます。 これを設定するには、最初に Active Directory を Azure Active Directory と同期し、次に、Windows 10 デバイスを Azure AD に登録して、Microsoft 365 Business によるモバイルデバイス管理用に登録します。
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Microsoft 365 Business で管理するドメイン参加済みデバイスをセットアップする

オンプレミスの Active Directory に加えて Azure Active Directory によって提供される機能からメリットを得るために、組織のドメインに参加しているデバイスを設定するには、**ハイブリッド AZURE AD に参加**しているデバイスを実装します。 これらは、オンプレミスの Active Directory と Azure Active Directory の両方に参加しているデバイスです。 ハイブリッド Azure AD に参加しているデバイスは、Microsoft 365 Business で保護および管理することができます。 
  
Windows 10 デバイスをハイブリッド Azure AD に参加させ、Microsoft 365 Business で管理するには、以下の手順を実行します。
  
1. ユーザー、グループ、および連絡先をローカルの Active Directory から Azure Active directory に同期するには、「 [Set up Directory synchronization For Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)」の説明に従って、ディレクトリ同期ウィザードと Azure Active directory Connect を実行します。
    
    > [!NOTE]
    > この手順は、Microsoft 365 Business の場合とまったく同じです。 
  
2. 手順3を実行して、Windows 10 デバイスがハイブリッド Azure AD に参加できるようにするには、次の前提条件を満たしていることを確認する必要があります。

   - Azure AD connect の最新バージョンを実行していること。

   - Azure AD connect は、ハイブリッド Azure AD に参加させるデバイスのすべてのコンピューターオブジェクトを同期しています。 コンピューターオブジェクトが特定の組織単位 (OU) に属している場合は、それらの Ou が Azure AD connect の同期にも設定されていることを確認してください。
    
3. 既存のドメインに参加している Windows 10 デバイスをハイブリッド Azure AD に登録し、Intune によるモバイルデバイス管理のために登録する (Microsoft 365 Business):
    
4. [ハイブリッド Azure Active Directory に参加しているデバイスを構成する方法](https://go.microsoft.com/fwlink/p/?linkid=872870)について、手順に従って操作します。 これにより、オンプレミスの Active Directory に参加している Windows 10 台のコンピューターの同期を有効にして、クラウドの準備を行うことができます。
    
5. モバイルデバイスの管理用に Windows 10 デバイスを登録するには、「[グループポリシーを使用して windows 10 デバイスを Intune に登録](https://go.microsoft.com/fwlink/p/?linkid=872871)する (手順については)」を参照してください。 グループポリシーの設定は、ローカルコンピューターレベルまたは一括操作に対して行うことができ、ドメインコントローラーサーバー上でこのグループポリシー設定を作成することができます。