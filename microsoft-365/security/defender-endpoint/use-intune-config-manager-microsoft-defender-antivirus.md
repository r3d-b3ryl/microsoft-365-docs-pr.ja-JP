---
title: Microsoft エンドポイント マネージャーを使用してMicrosoft Defender ウイルス対策を構成する
description: Microsoft エンドポイント マネージャーとMicrosoft Intuneを使用してMicrosoft Defender ウイルス対策とEndpoint Protectionを構成する
keywords: scep、intune、エンドポイント保護、構成
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.collection: m365-security-compliance
ms.openlocfilehash: b25e57ee28ae0ef3f219a9adda1ff3f860d063db
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/12/2022
ms.locfileid: "64789296"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a>Microsoft エンドポイント マネージャーを使用してMicrosoft Defender ウイルス対策を構成および管理する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**

- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender ウイルス対策

**プラットフォーム**
- Windows

[Microsoft エンドポイント マネージャー](/mem/endpoint-manager-overview)を使用して、Microsoft Defender ウイルス対策 スキャンを構成できます。 [Microsoft Intune](/mem/intune/fundamentals/what-is-intune)と[Configuration Manager](/mem/configmgr/core/understand/introduction)がエンドポイント マネージャーの一部になりました。

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a>エンドポイント マネージャーでMicrosoft Defender ウイルス対策 スキャンを構成する

1. Microsoft エンドポイント マネージャー管理センター ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) に移動し、サインインします。

2. **Endpoint Security** に移動します。

3. [ **管理**] で [ **ウイルス対策**] を選択します。

4. Microsoft Defender ウイルス対策 ポリシーを選択します。

5. [**管理**] で [**プロパティ**] を選択します。

6. **[構成の設定]** の横にある **[編集]** を選択します。

   > [!IMPORTANT]
   > AllowOnAccessProtection と AllowIntrusionPreventionSystem ウイルス対策の設定は正式に非推奨になっており、構成できません。 

7. [ **スキャン** ] セクションを展開し、スキャン設定を確認または編集します。

8. [ **校閲+ 保存**] を選択します。

> [!TIP]
> お困りの際は、 [Microsoft Intuneでのエンドポイント セキュリティの管理に関するページを参照](/mem/intune/protect/endpoint-security)してください。

> [!TIP]
> 他のプラットフォームのウイルス対策関連情報を探している場合は、次を参照してください。
> - [macOS でMicrosoft Defender for Endpointの基本設定を設定する](mac-preferences.md)
> - [Mac 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [IntuneのMicrosoft Defender ウイルス対策の macOS ウイルス対策ポリシー設定](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [Linux でMicrosoft Defender for Endpointの基本設定を設定する](linux-preferences.md)
> - [Linux 用 Microsoft Defender for Endpoint](microsoft-defender-endpoint-linux.md)
> - [Android の機能で Defender for Endpoint を構成する](android-configure.md)
> - [iOS 機能でMicrosoft Defender for Endpointを構成する](ios-configure-features.md)

## <a name="related-articles"></a>関連記事

- [管理ツールと構成ツールのリファレンス 記事](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender ウイルス対策 (Windows 10)](microsoft-defender-antivirus-in-windows-10.md)
