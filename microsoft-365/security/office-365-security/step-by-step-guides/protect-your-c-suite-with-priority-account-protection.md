---
title: Microsoft Defender for Office 365 プラン 2 で優先度アカウント保護を使用して c スイートを保護する
description: 優先度の高いアカウント保護を使用して c スイートを保護する手順。 アカウントを優先度アカウントとしてタグ付けすると、会社の幹部を対象とするメール フロー パターンに合わせて調整された追加の保護と、レポート、アラート、および調査の可視性が向上します。
search.product: ''
search.appverid: ''
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-guidance-templates
ms.topic: how-to
ms.technology: mdo
ms.openlocfilehash: de0de8b418036d6b8e73b9cf5ec8deafc24af6a9
ms.sourcegitcommit: 7e551fa4e9b8b25ed62b5f406143b6b1dae08cbf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2022
ms.locfileid: "67106495"
---
# <a name="protect-your-c-suite-with-priority-account-protection"></a>優先度の高いアカウント保護で c スイートを保護する

優先度アカウント保護は、IT チームとセキュリティ チームが組織内の重要なユーザーに対して高品質のサービスと保護を確保するのに役立ちます。 アカウントを優先度アカウントとしてタグ付けすると、会社の幹部を対象とするメール フロー パターンに合わせて調整された追加の保護と、レポート、アラート、および調査の可視性が向上します。

## <a name="what-youll-need"></a>必要なもの
- Microsoft Defender for Office 365 プラン 2 (E5 プランの一部として含まれる)
- 十分なアクセス許可 (セキュリティ管理者ロール)
- 次の手順を実行するには、5 分かかります。

## <a name="tag-priority-users"></a>優先度の高いユーザーにタグを付けます
1. 優先度アカウントとしてタグ付けするユーザー、グループ、またはドメインを特定します。
1. [Microsoft Security Portal](https://security.microsoft.com/) にログインし、左側のナビゲーション バーの [設定] に移動します。
1. 読み込むページでEmail &コラボレーションを選択し、[ユーザー タグ] をクリックします。
1. [ユーザー タグ] ページで、[優先度] アカウント タグを選択し、[タグの編集] を押します
1. 表示されるポップアップで、[メンバーの追加] を選択します。
1. タグ付けするユーザーを検索し、1 人以上のユーザーを選択して [追加] を押します
1. 選択したメンバーを確認し、[次へ] を押します。
1. 送信キーを押して変更を確認する

優先度アカウント タグの詳細については、「[優先度アカウントの管理と監視 - Microsoft 365 管理者|Microsoft Docs](../../../admin/setup/priority-accounts.md)。

## <a name="next-steps"></a>次の手順
[優先度アカウントとしてタグ付けされたユーザーの区別された保護を確認します](../../office-365-security/configure-review-priority-account.md)。

## <a name="powershell-configuration"></a>PowerShell 構成
[PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) を使用してこれらの手順を実行する場合は、次のコマンドレットを使用してこれを行うことができます。
1. 優先度アカウントの一覧を表示する: **Get-User -Is VIP | ID を選択** する
1. 優先度アカウントの一覧にユーザーを追加する: **Set-User -VIP:$true -Identity \<Identity\>**
1. 優先度アカウントの一覧からユーザーを削除する: **Set-User -VIP:$false -Identity \<Identity\>**
