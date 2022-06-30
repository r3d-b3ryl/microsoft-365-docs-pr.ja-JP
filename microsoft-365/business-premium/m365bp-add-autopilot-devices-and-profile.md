---
title: ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.localizationpriority: high
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: be5b6d90-3344-4c5e-bf40-5733eb845beb
description: Windows Autopilot を使用して、ビジネス用に新し いWindows 10 デバイスをセットアップし、従業員が使用できるようにする方法を学びます。
ms.openlocfilehash: 4ab7925f751d987e9508732202908ad10c9d46b7
ms.sourcegitcommit: d1b60ed9a11f5e6e35fbaf30ecaeb9dfd6dd197d
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/29/2022
ms.locfileid: "66491135"
---
# <a name="use-this-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する

Windows Autopilot を使用して、ビジネス用に **新しい** Windows 10 デバイスをセットアップし、従業員に提供するときにすぐに使用できるようにすることができます。
  
## <a name="device-requirements"></a>デバイスの要件

デバイスは次の要件を満たしている必要があります。
  
- Windows 10 バージョン 1703 以降

- Windows out-of-box experience を行っていない新しいデバイス

## <a name="use-the-setup-guide-to-add-devices-and-profiles"></a>セットアップ ガイドを使用して、デバイスとプロファイルを作成する

デバイス グループまたはプロファイルをまだ作成していない場合は、ステップバイステップ ガイドを使用して開始するのが最善の方法です。 [Autopilot デバイスを追加](m365bp-create-and-edit-Autopilot-devices.md)し、ガイドを使用せずに[プロファイルを割り当てる](../admin/devices/create-and-edit-Autopilot-profiles.md)こともできます。
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。

2. 左側のナビゲーション ウィンドウで **[デバイス]** \> **[Autopilot]** の順に選びます。

    ![管理センターでデバイスを選択し、Autopilot を選択します。](../media/Autopilot.png)
  
3. **[Autopilot]** ページで、**[スタート ガイド]** をクリックまたはタップします。

    ![Click Start guide for step-by-step instructions for Autopilot.](../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
4. **[デバイスの一覧を含む .csv ファイルのアップロード]** ページで、準備した .CSV ファイルがある場所を参照して、**[開く]** \> **[次へ]** の順に選択します。ファイルには次の 3 つのヘッダーがあります。 

    - 列 A:デバイスのシリアル番号
    - 列 B:Windows 製品 ID
    - 列 C:ハードウェア ハッシュ

この情報は、ハードウェアの製造元から、または CSV ファイルを生成する [Get-WindowsAutopilotInfo PowerShell スクリプト](https://www.powershellgallery.com/packages/Get-WindowsAutopilotInfo) を使って、入手できます。

詳細については、[デバイスの一覧の CSV ファイル](../admin/misc/device-list.md)を参照してください。また、[ **デバイスの一覧を含む .csv ファイルのアップロード**] ページでサンプル ファイルをダウンロードすることもできます。

> [!NOTE]
> このスクリプトは、WMIを 使用して、顧客がデバイスを Windows Autopilot に登録するために必要なプロパティを取得します。 結果の CSV ファイルが Windows 製品 ID (PKID) 値を収集しないのは通常のことです。これは、デバイスを登録するために必要ではなく、出力 CSV で PKID が NULL であってもまったく問題がないためです。 シリアル番号とハードウェア ハッシュのみが設定されます。

5. **[プロファイルの割り当て]** ページで、既存のプロファイルを選択するか、新しいプロファイルを作成します。まだプロファイルがない場合は、作成するように求めるメッセージが表示されます。

    プロファイルは、1 つのデバイスまたはデバイスのグループに適用できる設定のコレクションです。

    既定の機能は必須であり、自動的に設定されます。既定の機能は次のとおりです。

    - Cortana、OneDrive、OEM の登録のスキップ。

    - 会社のブランドを含む、サインイン エクスペリエンスを作成します。

    - デバイスを Azure Active Directory アカウントに接続し、Microsoft 365 Business Premium によって管理されるようにデバイスを自動的に登録します。

    詳細については、「[Autopilot プロファイルの設定について](m365bp-Autopilot-profile-settings.md)」を参照してください。

6. 他の設定には、[ **プライバシーの設定をスキップする**] や [ **ユーザーがローカルの管理者になることを許可しない**] があります。既定では、両方が [ **オフ**] に設定されます。

    [ **次へ**] を選びます。

7. **[完了しました]** では、作成 (または選択) したプロファイルが、デバイスの一覧をアップロードして作成したデバイス グループに適用されることを示しています。デバイスのユーザーが次にサインインすると、これらの設定が有効になります。**[閉じる]** を選びます。

## <a name="related-content"></a>関連コンテンツ

- [Autopilot プロファイルの設定について](../business-premium/m365bp-Autopilot-profile-settings.md)
- [デバイスとアプリ データを保護するためのオプション](../admin/devices/choose-device-security.md) (記事)
- [ビジネス プランの Microsoft 365 をセキュリティで保護するためのベスト プラクティス](../admin/security-and-compliance/secure-your-business-data.md)
