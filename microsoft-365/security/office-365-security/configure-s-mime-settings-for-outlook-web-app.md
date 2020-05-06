---
title: S/MIME 設定の構成-web 上の Outlook の Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c7dee22c-9b5b-425c-91a9-d093204ff84e
ms.collection:
- M365-security-compliance
description: Exchange online の Outlook on the web で S/MIME 設定を表示および構成するために必要な Exchange Online 管理者の簡単な説明。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2ed3f3c6289c4663c6bebecdf9ab03eacd94e373
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035096"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Outlook on the web を使用して、Exchange Online の S/MIME 設定を構成する

Exchange Online の管理者は、S/MIME で保護されたメッセージを送受信できるように、Outlook on the web (旧称 Outlook Web App) をセットアップできます。 Exchange Online PowerShell でこの機能を表示および管理するには、 **-smimeconfig**コマンドレットおよび**Set-smimeconfig**コマンドレットを使用します。 Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。

構文およびパラメーターの詳細については、「 [Get-smimeconfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/get-smimeconfig) 」および「 [Set-smimeconfig](https://docs.microsoft.com/powershell/module/exchange/encryption-and-certificates/set-smimeconfig)」を参照してください。

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>新しい Microsoft Edge (Chromium ベース) に関する考慮事項

Web 上の Outlook で S/MIME を新しい[Microsoft edge](https://www.microsoft.com/windows/microsoft-edge) web ブラウザーで使用するには、microsoft edge の新しい microsoft Edge に microsoft S/mime 拡張機能をインストールするために、ユーザー (または別の管理者) が、 **Extensioninstallforcelist**という microsoft edge browser policy を設定および構成する必要があります。 ポリシーの値は`maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`です。 このポリシーを適用するには、ドメインに参加しているコンピューターが必要であるため、新しい Microsoft Edge ブラウザーで S/MIME を使用するとドメインに参加しているコンピューターが効果的に必要になります。

**Extensioninstallforcelist**ポリシーの詳細については、「 [extensioninstallforcelist](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)」を参照してください。

この手順は、新しい Microsoft Edge を使用するための前提条件です。ユーザーによってインストールされた S/MIME コントロールは置き換えられません。 S/MIME の初めての使用時に、S/MIME コントロールをダウンロードして、web 上の Outlook にインストールするようにユーザーに求められます。 または、ユーザーが Outlook on the web 設定で**S/MIME**を事前に参照して、コントロールのダウンロードリンクを取得することができます。

## <a name="considerations-for-chrome"></a>Chrome の考慮事項

Google Chrome web ブラウザーで Outlook on the web で S/MIME を使用するには、ユーザー (または別の管理者) が**Extensioninstallforcelist**という名前の Chromium ポリシーを設定および構成して、Microsoft S/mime 拡張機能を Chrome にインストールする必要があります。 ポリシーの値は`maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx`です。 このポリシーを適用するには、ドメインに参加しているコンピューターが必要であるため、Chrome で S/MIME を使用するとドメインに参加しているコンピューターが効果的に必要になります。

**Extensioninstallforcelist**ポリシーの詳細については、「 [extensioninstallforcelist](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)」を参照してください。

この手順は、Chrome を使用するための前提条件です。ユーザーによってインストールされた S/MIME コントロールは置き換えられません。 S/MIME の初めての使用時に、S/MIME コントロールをダウンロードして、web 上の Outlook にインストールするようにユーザーに求められます。 または、ユーザーが Outlook on the web 設定で**S/MIME**を事前に参照して、コントロールのダウンロードリンクを取得することができます。

## <a name="for-more-information"></a>詳細情報

[S/MIME によるメッセージの署名と暗号化](s-mime-for-message-signing-and-encryption.md)
