---
title: S/MIME 設定の構成 - Outlook on web の Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange Online の Web 上の Outlook で S/MIME 設定を表示および構成するために Exchange Online 管理者が行う必要がある作業について、簡単に説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9acd7d4523754c1e07ece8fb0344d9f888c0ee3d
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825703"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Outlook on the web 用に Exchange Online で S/MIME 設定値を構成する

Exchange Online の管理者は、S/MIME 保護メッセージの送受信を可能にするために、Web 上の Outlook (Outlook Web App) をセットアップできます。 **Get-SmimeConfig コマンドレットおよび** **Set-SmimeConfig**コマンドレットを使用し、Exchange Online PowerShell でこの機能を表示および管理します。 Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

構文およびパラメーターの詳細については[、「Get-SmimeConfig」および](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)[「Set-SmimeConfig」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)。

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>新しい Microsoft Edge (Chromium ベース) に関する考慮事項

新しい Microsoft Edge Web ブラウザーの Web 上の Outlook で S/MIME を使用するには、新しい [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) で Microsoft S/MIME 拡張機能をインストールするには、管理者 (または別の管理者) が設定および構成する必要があります。このポリシーでは **、ExtensionInstallForcelist** という名前の Microsoft Edge ブラウザー ポリシーを設定および構成する必要があります。 ポリシーの値は `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` このポリシーを適用するには、ドメインに参加しているデバイスまたは Azure AD に参加しているデバイスが必要です。したがって、新しい Microsoft Edge ブラウザーで S/MIME を使うには、ドメインに参加しているデバイスまたは Azure AD 参加済みデバイスが効果的です。

**ExtensionInstallForcelist ポリシーの詳細については**[、ExtensionInstallForcelist を参照してください](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)。

この手順は、新しい Microsoft Edge を使用するための前提条件です。ユーザーによってインストールされる S/MIME コントロールを置き換えるのでない。 ユーザーは、S/MIME を初めて使用する場合に、S/MIME コントロールを Web 上の Outlook にダウンロードしてインストールするように求められます。 または、Web 上の Outlook の設定で **S/MIME** に移動して、コントロールのダウンロード リンクを取得することもできます。

## <a name="considerations-for-chrome"></a>Chrome に関する考慮事項

Google Chrome Web ブラウザーの Web 上の Outlook で S/MIME を使用するには、Chrome で Microsoft S/MIME 拡張機能をインストールするには、ユーザー (または別の管理者) が **ExtensionInstallForcelist** という名前の Chromium ポリシーを設定して構成する必要があります。 ポリシーの値は `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` このポリシーを適用するには、ドメインに参加しているコンピューターが必要になります。Chrome で S/MIME を使うには、ドメインに参加しているコンピューターが効果的です。

**ExtensionInstallForcelist ポリシーの詳細については**[、ExtensionInstallForcelist を参照してください](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)。

この手順は、Chrome を使うための前提条件です。ユーザーによってインストールされる S/MIME コントロールを置き換えるのでない。 ユーザーは、S/MIME を初めて使用する場合に、S/MIME コントロールを Web 上の Outlook にダウンロードしてインストールするように求められます。 または、Web 上の Outlook の設定で **S/MIME** に移動して、コントロールのダウンロード リンクを取得することもできます。

## <a name="for-more-information"></a>詳細情報

[S/MIME によるメッセージの署名と暗号化](s-mime-for-message-signing-and-encryption.md)
