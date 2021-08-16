---
title: インターフェイスをMicrosoft Defender ウイルス対策する
description: アプリでウイルスと脅威の保護タイルをWindows セキュリティできます。
keywords: ui lockdown, headless mode, hide app, hide settings, hide interface
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 66f9f571411c61bd8944ceb01a13f237ecd1d483
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/13/2021
ms.locfileid: "58255784"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>ユーザーがユーザー インターフェイスを表示または操作Microsoft Defender ウイルス対策防止する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

グループ ポリシーを使用すると、エンドポイント上のユーザーにインターフェイスが表示Microsoft Defender ウイルス対策できます。 また、スキャンの一時停止を防止することもできます。

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>インターフェイスをMicrosoft Defender ウイルス対策する

このWindows 10バージョン 1703 では、インターフェイスを非表示にすると、Microsoft Defender ウイルス対策 通知が非表示にされ、ウイルス & の脅威保護タイルが Windows セキュリティ アプリに表示されWindows セキュリティされます。

設定を [有効] に **設定します**。

:::image type="content" source="../../media/wdav-headless-mode-off-1703.png" alt-text="シールド アイコンWindows セキュリティウイルスと脅威の保護のセクションを含むファイルのスクリーンショット":::

設定が [無効] または **[** 構成されていない] に設定されている場合:

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="シールド アイコンとWindows セキュリティ保護セクションを含むアプリのスクリーンショット":::

>[!NOTE]
>インターフェイスを非表示にすることで、Microsoft Defender ウイルス対策通知がエンドポイントに表示されるのを防ぐことも可能です。 Microsoft Defender for Endpoint 通知は引き続き表示されます。 エンドポイントに表示 [される通知を個別に構成することもできます](configure-notifications-microsoft-defender-antivirus.md)

以前のバージョンの Windows 10設定では、クライアント インターフェイスWindows Defender非表示になります。 ユーザーが開くしようとすると、「システム管理者は、このアプリへのアクセスを制限しました」という警告が表示されます。

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="1703 より前のバージョンの Windows 10でヘッドレス モードが有効になっている場合の警告メッセージ":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>グループ ポリシーを使用して Microsoft Defender AV インターフェイスをユーザーから非表示にする

1. グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー管理 **エディターを使用して、[コンピューター** の構成] **に移動します**。

3. [管理 **用テンプレート] をクリックします**。

4. ツリーを展開して **、Windowsインターフェイス> Microsoft Defender ウイルス対策 >コンポーネントを表示します**。

5. [ヘッドレス UI モードを有効にする] **設定を** ダブルクリックし、オプションを [有効] に **設定します**。 **[OK]** をクリックします。 

ユーザー [が PC の保護を](configure-local-policy-overrides-microsoft-defender-antivirus.md) 変更する方法の詳細については、「ユーザーがポリシー設定をローカルで変更するのを防ぐ」を参照してください。

## <a name="prevent-users-from-pausing-a-scan"></a>ユーザーによるスキャンの一時停止を防止する

ユーザーがスキャンを一時停止するのを防ぐと、スケジュールされたスキャンまたはオンデマンド スキャンがユーザーによって中断されないのに役立ちます。

> [!NOTE]
> この設定は、この設定ではWindows 10。

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>グループ ポリシーを使用して、ユーザーによるスキャンの一時停止を防止する

1. グループ ポリシー管理マシンで、グループ ポリシー [管理](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)コンソールを開き、構成するグループ ポリシー オブジェクトを右クリックし、[編集] をクリック **します**。

2. グループ ポリシー管理 **エディターを使用して、[コンピューター** の構成] **に移動します**。

3. [管理 **用テンプレート] をクリックします**。

4. ツリーを展開して、[**スキャン] WindowsコンポーネントMicrosoft Defender ウイルス対策**  >    >  **展開します**。

5. [ユーザーにスキャンの **一時停止を許可する** ] 設定をダブルクリックし、オプションを [無効] に **設定します**。 **[OK]** をクリックします。 

## <a name="related-articles"></a>関連記事

- [エンドポイントに表示される通知を構成する](configure-notifications-microsoft-defender-antivirus.md)

- [ユーザーとのエンド ユーザー操作を構成Microsoft Defender ウイルス対策](configure-end-user-interaction-microsoft-defender-antivirus.md)

- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
