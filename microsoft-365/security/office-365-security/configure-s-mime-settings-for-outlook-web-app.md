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
description: Exchange Online の Outlook on the web で S/MIME 設定を表示および構成するために Exchange Online 管理者が行う必要がある操作の簡単な説明。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2ccadfc46e42713601b115c18a119e48dcfdcbf4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290035"
---
# <a name="configure-smime-settings-in-exchange-online-for-outlook-on-the-web"></a>Exchange Online for Outlook on the web で S/MIME 設定を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Exchange Online の管理者は、Web 上の Outlook (旧称 Outlook Web App) を設定して、S/MIME で保護されたメッセージの送受信を許可できます。 **Get-SmimeConfig コマンドレットと** **Set-SmimeConfig** コマンドレットを使用して、Exchange Online PowerShell でこの機能を表示および管理します。 Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

構文およびパラメーターの詳細については [、「Get-SmimeConfig」](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig) および [「Set-SmimeConfig」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)。

## <a name="considerations-for-new-microsoft-edge-chromium-based"></a>新しい Microsoft Edge (Chromium ベース) に関する考慮事項

新しい [Microsoft Edge](https://www.microsoft.com/windows/microsoft-edge) Web ブラウザーで Outlook on the web で S/MIME を使用するには、お客様 (または別の管理者) が **ExtensionInstallForcelist** という名前の Microsoft Edge ブラウザー ポリシーを設定して構成し、Microsoft S/MIME 拡張を新しい Microsoft Edge にインストールする必要があります。 ポリシー値は次の値です `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 。 また、このポリシーを適用するには、ドメインに参加しているデバイスまたは Azure AD に参加しているデバイスが必要なので、新しい Microsoft Edge ブラウザーで S/MIME を使用するには、ドメインに参加しているデバイスまたは Azure AD に参加しているデバイスが効果的に必要です。

**ExtensionInstallForcelist ポリシーの詳細については**[、「ExtensionInstallForcelist」を参照してください](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#extensioninstallforcelist)。

この手順は、新しい Microsoft Edge を使用する場合の前提条件です。ユーザーによってインストールされた S/MIME コントロールは置き換えされません。 ユーザーは、S/MIME を初めて使用する際に、Web 上の Outlook で S/MIME コントロールをダウンロードしてインストールするように求めるメッセージが表示されます。 または、ユーザーは Outlook on the web の設定で **S/MIME** に事前に移動して、コントロールのダウンロード リンクを取得できます。

## <a name="considerations-for-chrome"></a>Chrome に関する考慮事項

Google Chrome Web ブラウザーの Outlook on the web で S/MIME を使用するには、ユーザー (または別の管理者) が **ExtensionInstallForcelist** という名前の Chromium ポリシーを設定して構成し、Microsoft S/MIME 拡張機能を Chrome にインストールする必要があります。 ポリシー値は次の値です `maafgiompdekodanheihhgilkjchcakm;https://outlook.office.com/owa/SmimeCrxUpdate.ashx` 。 また、このポリシーを適用するにはドメインに参加しているコンピューターが必要なので、Chrome で S/MIME を使用するには、ドメインに参加しているコンピューターが効果的に必要になります。

**ExtensionInstallForcelist ポリシーの詳細については**[、「ExtensionInstallForcelist」を参照してください](https://cloud.google.com/docs/chrome-enterprise/policies/?policy=ExtensionInstallForcelist)。

この手順は、Chrome を使用する場合の前提条件です。ユーザーによってインストールされた S/MIME コントロールは置き換えされません。 ユーザーは、S/MIME を初めて使用する際に、Web 上の Outlook で S/MIME コントロールをダウンロードしてインストールするように求めるメッセージが表示されます。 または、ユーザーは Outlook on the web の設定で **S/MIME** に事前に移動して、コントロールのダウンロード リンクを取得できます。

## <a name="for-more-information"></a>詳細情報

[S/MIME によるメッセージの署名と暗号化](s-mime-for-message-signing-and-encryption.md)
