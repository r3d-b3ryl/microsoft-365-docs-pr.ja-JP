---
title: S/MIME 設定を構成する - Exchange Online for Outlook on web
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange Online の Outlook on the Web で S/MIME 設定を表示および構成するために Exchange Online 管理者が行う必要がある操作の簡単な説明。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6eacc6a264682474054d0d3546b831039bee9a0c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065371"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Exchange Online for Outlook on the web で S/MIME 設定を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online の管理者として、Outlook on the web (以前は Outlook Web App) をセットアップして、S/MIME で保護されたメッセージの送受信を許可できます。 **Get-SmimeConfig コマンドレット** と **Set-SmimeConfig** コマンドレットを使用して、Exchange Online PowerShell でこの機能を表示および管理します。 Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

構文とパラメーターの詳細については [、「Get-SmimeConfig」](/powershell/module/exchange/get-smimeconfig) および [「Set-SmimeConfig」を参照してください](/powershell/module/exchange/set-smimeconfig)。

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>新しい Microsoft Edge (クロム ベース) の考慮事項

新しい Microsoft [Edge](https://www.microsoft.com/windows/microsoft-edge) Web ブラウザーで Outlook on the web で S/MIME を使用するには **、ExtensionInstallForcelist** という名前の Microsoft Edge ブラウザー ポリシーを設定して構成し、Microsoft S/MIME 拡張機能を新しい Microsoft Edge にインストールする必要があります。 ポリシー値はです `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 。 また、このポリシーを適用するには、ドメインに参加しているデバイスまたは Azure AD に参加しているデバイスが必要なので、新しい Microsoft Edge ブラウザーで S/MIME を使用するには、ドメインに参加しているデバイスまたは Azure AD に参加しているデバイスが効果的に必要です。

**ExtensionInstallForcelist ポリシーの詳細については**[、「ExtensionInstallForcelist」を参照してください](/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)。

この手順は、新しい Microsoft Edge を使用する前提条件です。ユーザーがインストールした S/MIME コントロールは置き換えされません。 ユーザーは、S/MIME の最初の使用時に Outlook on the web で S/MIME コントロールをダウンロードしてインストールするように求めるメッセージが表示されます。 または、ユーザーは Outlook on the Web 設定で積極的に **S/MIME** に移動して、コントロールのダウンロード リンクを取得できます。

## <a name="considerations-for-chrome"></a>Chrome の考慮事項

Google Chrome Web ブラウザーの Outlook on the web で S/MIME を使用するには、Chrome に Microsoft S/MIME 拡張機能をインストールするように **ExtensionInstallForcelist** という名前のクロム ポリシーを設定および構成する必要があります。 ポリシー値はです `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 。 また、このポリシーを適用するにはドメインに参加しているコンピューターが必要なので、Chrome で S/MIME を使用するには、ドメインに参加しているコンピューターが効果的に必要です。

**ExtensionInstallForcelist ポリシーの詳細については**[、「ExtensionInstallForcelist」を参照してください](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)。

この手順は、Chrome を使用する前提条件です。ユーザーがインストールした S/MIME コントロールは置き換えされません。 ユーザーは、S/MIME の最初の使用時に Outlook on the web で S/MIME コントロールをダウンロードしてインストールするように求めるメッセージが表示されます。 または、ユーザーは Outlook on the Web 設定で積極的に **S/MIME** に移動して、コントロールのダウンロード リンクを取得できます。

## <a name="for-more-information"></a>詳細情報

[S/MIME によるメッセージの署名と暗号化](s-mime-for-message-signing-and-encryption.md)