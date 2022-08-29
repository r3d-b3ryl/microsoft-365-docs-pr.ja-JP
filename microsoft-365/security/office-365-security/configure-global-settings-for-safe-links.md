---
title: Defender for Office 365でセーフ リンク設定のグローバル設定を構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理者は、Microsoft Defender for Office 365のセーフ リンクのグローバル設定 ([次の URL をブロックする] の一覧とOffice 365 アプリの保護) を表示および構成する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d396157be6e245e81d084d97dfc6446201b28f95
ms.sourcegitcommit: d09eb780dc41a01796eb8137fbe9267231af6746
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/19/2022
ms.locfileid: "67385751"
---
# <a name="configure-global-settings-for-safe-links-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365でセーフ リンクのグローバル設定を構成する

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> この記事は、[Microsoft Defender for Office 365](defender-for-office-365.md) をご利用の法人のお客様を対象としています。 Outlook の Safelinks に関する情報を探しているホーム ユーザーの場合は、 [高度な Outlook.com セキュリティ](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)に関するページを参照してください。

セーフ リンクは[、メール](defender-for-office-365.md) フロー内の受信電子メール メッセージの URL スキャンと、電子メール メッセージやその他の場所での URL とリンクのクリック確認の時間を提供する、Microsoft Defender for Office 365の機能です。 詳細については、「[Microsoft Defender for Office 365のセーフ リンク](safe-links.md)」を参照してください。

サポートされている Office アプリのセーフ リンク設定を含め、セーフ リンク ポリシーでセーフ [リンクのほとんどの設定を構成します](safe-links.md#safe-links-settings-for-office-apps)。 手順については、「[Microsoft Defender for Office 365 で安全なリンク ポリシーを設定する](set-up-safe-links-policies.md)」を参照してください。

ただし、セーフ リンクでは、セーフ リンク ポリシー自体の外部で構成する次のグローバル設定も使用されます。

- [ **次の URL をブロックする]** の一覧。 この設定は、アクティブなセーフ リンク ポリシーに含まれるすべてのユーザーに適用されます。 詳細については、[安全なリンクの「次の URL をブロックする」の一覧を](safe-links.md#block-the-following-urls-list-for-safe-links)参照してください。

グローバル セーフ リンク設定は、Microsoft 365 Defender ポータルまたは PowerShell で構成できます (Exchange Onlineにメールボックスを含む対象となる Microsoft 365 組織の PowerShell Exchange Online、Exchange Onlineのない組織向けのスタンドアロン EOP PowerShellメールボックスが、Microsoft Defender for Office 365アドオン サブスクリプションの場合)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- 既定のセーフ リンク ポリシーはありませんが、 **組み込みの保護** プリセット セキュリティ ポリシーは、すべての受信者 (カスタムのセーフ リンク ポリシーまたは Standard または Strict プリセットのセキュリティ ポリシーで定義されていないユーザー) に安全なリンク保護を提供します。 詳しくは、「[EOP と Microsoft Defender for Office 365 の事前設定されたセキュリティ ポリシー](preset-security-policies.md)」を参照してください。 セーフ リンク ポリシーを作成して、特定のユーザー、グループ、またはドメインに適用することもできます。 手順については、「[Microsoft Defender for Office 365 で安全なリンク ポリシーを設定する](set-up-safe-links-policies.md)」を参照してください。

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[安全なリンク**] ページに直接移動するには、 <https://security.microsoft.com/safelinksv2>.

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - セーフ リンクのグローバル設定を構成するには、 **組織の管理** または **セキュリティ管理者** の役割グループのメンバーである必要があります。
  - 安全なリンクのグローバル設定への読み取り専用アクセスを行うには、 **グローバル リーダー** または **セキュリティ 閲覧者** ロール グループのメンバーである必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- セーフ リンクのグローバル設定に推奨される値については、「セーフ リンク [の設定](recommended-settings-for-eop-and-office365.md#safe-links-settings)」を参照してください。

- 新しいポリシーまたは更新されたポリシーを適用するには、最大 30 分かかります。

- [新機能はMicrosoft Defender for Office 365に継続的に追加されています](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365)。 新機能が追加されると、既存のセーフ リンク ポリシーの調整が必要になる場合があります。

## <a name="configure-the-block-the-following-urls-list-in-the-microsoft-365-defender-portal"></a>Microsoft 365 Defender ポータルで [次の URL をブロックする] 一覧を構成する

> [!NOTE]
> [テナント許可/ブロック リスト](allow-block-urls.md#use-the-microsoft-365-defender-portal-to-create-block-entries-for-urls-in-the-tenant-allowblock-list) で URL エントリのブロックを管理できるようになりました。 "次の URL をブロックする"リストは非推奨のプロセスです。 既存のエントリを "次の URL をブロックする" リストから移行し、テナント許可/ブロック リストの URL エントリをブロックします。 ブロックされた URL を含むメッセージは検疫されます。

**[次の URL をブロックする]** の一覧では、サポートされているアプリのセーフ リンク スキャンによって常にブロックする必要があるリンクを識別します。 詳細については、 [セーフ リンクの「次の URL をブロックする」の一覧を参照してください](safe-links.md#block-the-following-urls-list-for-safe-links)。

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[安全なリンク]** の順に移動します。 **[安全なリンク**] ページに直接移動するには、 <https://security.microsoft.com/safelinksv2>.

2. [ **安全なリンク** ] ページで、[ **グローバル設定**] をクリックします。 表示される **組織のセーフ リンク ポリシー** が表示されたら、[ **次の URL をブロックする** ] ボックスに移動します。

3. ["次の URL をブロックする" 一覧のエントリ構文](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)で説明されているように、1 つ以上のエントリを構成します。

   完了したら、**[保存]** をクリックします。

### <a name="configure-the-block-the-following-urls-list-in-powershell"></a>PowerShell で "次の URL をブロックする" 一覧を構成する

エントリ構文の詳細については、「 [次の URL をブロックする」の一覧のエントリ構文を参照してください](safe-links.md#entry-syntax-for-the-block-the-following-urls-list)。

**Get-AtpPolicyForO365** コマンドレットを使用して _、BlockURLs_ プロパティの既存のエントリを表示できます。

- 既存のエントリを置き換える値を追加するには、PowerShell または powerShell のExchange Online Protection Exchange Online次の構文を使用します。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "Entry1","Entry2",..."EntryN"
  ```

  この例では、次のエントリを一覧に追加します。

  - fabrikam.com のドメイン、サブドメイン、パスをブロックします。
  - サブドメインの調査をブロックしますが、tailspintoys.com の親ドメインやその他のサブドメインはブロックしません

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls "fabrikam.com","https://research.tailspintoys.com*"
  ```

- 他の既存のエントリに影響を与えずに値を追加または削除するには、次の構文を使用します。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}
  ```

  この例では、adatum.com の新しいエントリを追加し、fabrikam.com のエントリを削除します。

  ```powershell
  Set-AtpPolicyForO365 -BlockUrls @{Add="adatum.com"; Remove="fabrikam"}
  ```

## <a name="how-do-you-know-these-procedures-worked"></a>正常な動作を確認する方法

セーフ リンクのグローバル設定が正常に構成されたことを確認するには (**[次の URL をブロックする**] ボックスの一覧とアプリ保護設定Office 365)、次のいずれかの手順を実行します。

- Microsoft 365 Defender ポータルの **[安全なリンク**] ページで<https://security.microsoft.com/safelinksv2>、[**グローバル設定**] をクリックし、表示されるポップアップで設定を確認します。

- powerShell または powerShell Exchange Online Protection Exchange Onlineで、次のコマンドを実行し、設定を確認します。

  ```powershell
  Get-AtpPolicyForO365 | Format-List BlockUrls,EnableSafeLinksForO365Clients,AllowClickThrough,TrackClicks
  ```

  構文とパラメーターの詳細については、「 [Get-AtpPolicyForO365](/powershell/module/exchange/get-atppolicyforo365)」を参照してください。
