---
title: PowerShell を使用して Skype for Business Online を管理する
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: ''
ms.assetid: 054c16e6-9fd1-4e85-a0e6-81788b8410ea
description: PowerShell for Microsoft 365 を使用して、Skype for Business Online ポリシー、ユーザー単位ポリシー、会議の設定を管理します。
ms.openlocfilehash: 1c3a3e06d3fa607765382176a8c291fab2c69636
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65097670"
---
# <a name="manage-skype-for-business-online-with-powershell"></a>PowerShell を使用して Skype for Business Online を管理する

*この記事は、Microsoft 365 Enterprise および Office 365 Enterprise の両方に適用されます。*

Skype for Business Online 管理者は、ポリシーの管理を担当します。 これらのタスクの一部は Microsoft 365 管理センターで実行できますが、PowerShell で実行しやすいものもあります。

## <a name="before-you-start"></a>始める前に

> [!NOTE]
> Skype for Business Online Connector は現在、最新の Teams PowerShell モジュールに含まれています。 最新の **Teams PowerShell** パブリック リリースをご利用の場合は、Skype for Business Online Connector をインストールする必要はありません。

> [!NOTE]
> Skype for Business Online 管理者は、PowerShell を使用して **Teams** と **Skype for Business Online** の両方のアプリ ポリシーを管理できます。

[Teams PowerShell モジュール](/microsoftteams/teams-powershell-install)をインストールします。

## <a name="connect-using-admin-credentials"></a>管理者の資格情報を使用して接続する

1. Windows PowerShell コマンド プロンプト ウィンドを開き、次のコマンドを実行します:

   ```powershell
   Import-Module MicrosoftTeams
   $userCredential = Get-Credential
   Connect-MicrosoftTeams -Credential $userCredential
   ```

2. [**Windows PowerShell 資格情報の要求**] ダイアログ ボックスに管理者のアカウント名とパスワードを入力し、[**OK**] を選択します。

## <a name="connect-using-an-admin-account-with-multi-factor-authentication"></a>多要素認証の管理者アカウントを使用して接続する

1. Windows PowerShell コマンド プロンプト ウィンドを開いて次のコマンドを実行します:

   ```powershell
   Import-Module MicrosoftTeams
   Connect-MicrosoftTeams
   ```

2. ダイアログ ボックスが表示されたら、Skype for Business Online 管理者のアカウント名を入力します。

3. [**アカウントにサインイン**] ダイアログ ボックスで、Skype for Business Online 管理者のパスワードを入力し、[**サインイン**] を選択します。

4. [**アカウントにサインイン**] ダイアログ ボックスで手順に従い、確認コードなどのその他の認証情報を追加し、[**確認**] を選択します。

詳しくは、以下を参照してください。

- [PowerShell を使用して Skype for Business Online を管理する](manage-skype-for-business-online-policies-with-microsoft-365-powershell.md)

- [PowerShell を使用してユーザーごとに Skype for Business Online のポリシーを割り当てる](assign-per-user-skype-for-business-online-policies-with-microsoft-365-powershell.md)

## <a name="see-also"></a>関連項目

[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)

[Microsoft 365 用 PowerShell の使用を開始する](getting-started-with-microsoft-365-powershell.md)

[Skype for Business PowerShell のコマンドレット リファレンス](/powershell/module/skype/)
