---
title: 組織のパスワード有効期限ポリシーを設定します。
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 'Microsoft 365 管理センターで組織のパスワード有効期限ポリシーを設定する方法について説明します。 '
ms.openlocfilehash: a4d5f5240a6d4cca686b4809d05970b5e18b897f
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/27/2020
ms.locfileid: "44399580"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>組織のパスワード有効期限ポリシーを設定します。

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理センターは変更中です。 エクスペリエンスがここに表示されている詳細と一致しない場合は、「[新しい Microsoft 365 管理センターについて](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)」を参照してください。

::: moniker-end

この記事は、職場、学校、または非営利団体のパスワードの有効期限ポリシーを設定する管理者を対象としています。  

ユーザーの場合は、自分のパスワードを期限なしに設定する権限はありません。 職場または学校のテクニカル サポートに、この記事の手順を実行するように依頼してください。

管理者は、ユーザー パスワードを一定の日数が経過したら期限切れにするか、パスワードの有効期限が切れないように設定することができます。 

> [!Tip]
> 既定では、パスワードの有効期限は 90 日に設定されています。 最近の研究では、強制的なパスワードの変更はメリットよりデメリットの方が大きいことが強く示唆されています。 ハッカーが簡単に推測できる方法で、より弱いパスワードの選択、パスワードの再利用、または古いパスワードの更新をユーザーに促します。 パスワードを無期限に設定する場合は、[多要素認証](../security-and-compliance/set-up-multi-factor-authentication.md)を有効にすることをお勧めします。

特定の時間が経過するとユーザーのパスワードが期限切れになるように設定する場合は、以下の手順に従います。
> [!IMPORTANT]
> [グローバル管理者](../add-users/about-admin-roles.md)のみ次の手順を実行できます。
  
1. 管理センターで、[**設定**] \> [**設定**] の順に移動します。

2. [<a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">セキュリティとプライバシー</a>] ページに移動します。
 グローバル管理者でない場合は、[セキュリティとプライバシー] オプションは表示されません。
  
3. [**パスワードの有効期限ポリシー**] を選択します。
  
4. ユーザーがパスワードを変更する必要がないようにするには、[**数日後にユーザーのパスワードが期限切れになるように設定する**] の横のチェックボックスを選択します。
  
5. パスワードの有効期限が切れる頻度を入力します。 14 〜 730 の日数を選択します。
  
6. 2 つ目のボックスに、パスワードが期限切れになる前にユーザーに通知する日数を入力して、[ **保存** ] を選択します。 日数を 1 から 30 から選びます。
    
7. ユーザーのパスワードの有効期限が切れた場合は、画面の右下隅に通知が表示されます。
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>パスワードの有効期限機能に関する重要事項

2018 年 1 月現在、この機能については以下の点にご留意ください。
  
- Outlook アプリのみを使用するユーザーには、キャッシュで有効期限が切れるまで Microsoft 365 パスワードのリセットは強制されません。これは、実際に期限が切れた日から数日経過することがあります。管理者レベルでは、これに対する回避策はありません。
    
- ユーザーには、X 日後にパスワードの有効期限が切れる旨のメール通知が送られません。この機能は必要ですか? **[ここで投票してください。](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**
    
## <a name="prevent-last-password-from-being-used-again"></a>最後に使用したパスワードの再使用を禁止する

ユーザーが古いパスワードを再使用することを禁止する場合、Azure AD でこの操作を行うことができます。 「[パスワードの履歴を記録する](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/enforce-password-history)」を参照します。

また、従業員がモバイル デバイスを使用して Microsoft 365 にアクセスしている場合、それをワイプしてパスワードが保存されていないことを確認してください。 詳細については、「[元従業員のモバイル デバイスをワイプし、ブロックする](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device)」を参照してください。


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a>オンプレミスの Active Directory から Azure AD (Microsoft 365) へユーザー パスワード ハッシュを同期する

この記事は、クラウド専用ユーザー (Azure AD) の有効期限ポリシーを設定するユーザーを対象にしています。 パスワード ハッシュ同期、パススルー認証、または ADFS などのオンプレミスのフェデレーションを使用するハイブリッド ID ユーザーには適用されません。
  
ユーザー パスワード ハッシュをオンプレミスの AD から Azure AD に同期する方法については、「[Implement password hash synchronization with Azure AD Connect sync (Azure AD Connect 同期でパスワード ハッシュ同期を実装する)](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)」を参照してください。
