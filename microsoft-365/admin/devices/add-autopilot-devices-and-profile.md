---
title: ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection:
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.localizationpriority: medium
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
description: AutoPilot Windowsを使用して、従業員が使用できる状態Windows 10新しいデバイスをセットアップする方法について学習します。
ms.openlocfilehash: 12e86102633ddfc19960fb561b2a626da29f0560
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63314015"
---
# <a name="use-the-step-by-step-guide-to-add-autopilot-devices-and-profile"></a>ステップ バイ ステップ ガイドを使用して、Autopilot デバイスとプロファイルを追加する

> [!NOTE]
> Microsoft Defender for Business は、2022 年 3 月 1 日からMicrosoft 365 Business Premium顧客に展開しています。 この機能は、デバイスに追加のセキュリティ機能を提供します。 [Defender for Business の詳細については、「Defender for Business」を参照してください](../../security/defender-business/mdb-overview.md)。

AutoPilot Windowsを使用して、ビジネス用の新しい  Windows 10 デバイスをセットアップして、従業員に提供するときに使用できる状態にできます。
  
## <a name="device-requirements"></a>デバイスの要件

デバイスは、次の要件を満たす必要があります。
  
- Windows 10バージョン 1703 以降
    
- 最新のエクスペリエンスをWindowsした新しいデバイス
    
## <a name="use-the-setup-guide-to-create-devices-and-profiles"></a>セットアップ ガイドを使用して、デバイスとプロファイルを作成する

デバイス グループまたはプロファイルをまだ作成していない場合は、ステップ バイ ステップ ガイドを使用して開始してください。 ガイドを使用[せずに、デバイス](create-and-edit-autopilot-devices.md)[を追加](create-and-edit-autopilot-profiles.md)してプロファイルを割り当てすることもできます。 
  
1. <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> から管理センターにアクセスします。

2. 左側のナビゲーション ウィンドウで、[デバイスの **自動操縦]** \> **を選択します**。

    ![管理センターで、[デバイス] を選択し、[自動パイロット] を選択します。](../../media/AutoPilot.png)
  
2. [自動 **パイロット] ページで** 、[スタート ガイド] をクリックまたは **タップします**。
    
    ![Click Start guide for step-by-step instructions for Autopilot.](../../media/31662655-d1e6-437d-87ea-c0dec5da56f7.png)
  
3. [デバイスの **アップロード .csv** を含むファイル] ページで、準備されたファイルがある場所を参照.CSV、[次へ] を **開** \> **きます**。 ファイルには 3 つのヘッダーが必要です。
    
    - 列 A:デバイスのシリアル番号
    
    - 列 B:Windows 製品 ID
    
    - 列 C:ハードウェア ハッシュ
    
    この情報は、ハードウェア ベンダーから取得するか、 [Get-WindowsAutoPilotInfo PowerShell](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) スクリプトを使用して CSV ファイルを生成できます。 
    
    詳細については、[デバイスの一覧の CSV ファイル](../misc/device-list.md)を参照してください。また、[ **デバイスの一覧を含む .csv ファイルのアップロード**] ページでサンプル ファイルをダウンロードすることもできます。 
    
> [!NOTE]
> このスクリプトでは、WMI を使用して、ユーザーがデバイスを自動パイロットに登録するために必要Windowsします。 デバイスの登録には必須ではなく、出力 CSV で PKID が NULL である場合は完全に問題ありませんので、結果の CSV ファイルが Windows 製品 ID (PKID) 値を収集しないのは正常です。 シリアル番号とハードウェア ハッシュだけが設定されます。
    
4. [プロファイルの **割り当て] ページ** で、既存のプロファイルを選択するか、新しいプロファイルを作成できます。 まだ作成していない場合は、作成を求めるメッセージが表示されます。 
    
    プロファイルは、1 つのデバイスまたはデバイスのグループに適用できる設定のコレクションです。
    
    既定の機能は必須であり、自動的に設定されます。 既定の機能は次のとおりです。
    
    - [Cortana、OneDrive OEM 登録をスキップします。
    
    - 会社のブランドを含む、サインイン エクスペリエンスを作成します。
    
    - ConnectをアカウントにAzure Active Directoryし、デバイスによって管理されるアカウントを自動的に登録Microsoft 365 Business Premium。
    
    詳細については、「 [概要 - AutoPilot Profile settings」を参照してください](autopilot-profile-settings.md)。 
    
5. 他の設定には、[ **プライバシーの設定をスキップする**] や [ **ユーザーがローカルの管理者になることを許可しない**] があります。既定では、両方が [ **オフ**] に設定されます。 
    
    [ **次へ**] を選びます。
    
6. **完了すると、** 作成した (または選択した) プロファイルが、デバイスの一覧をアップロードして作成したデバイス グループに適用されます。 設定は、デバイス ユーザーが次にサインインするときに有効になります。 **[閉じる]** を選択します。

## <a name="related-content"></a>関連コンテンツ

[概要 - AutoPilot プロファイルの設定](autopilot-profile-settings.md) (記事)\
[デバイスとアプリ データを保護](../devices/choose-device-security.md)するためのオプション (記事) ビジネス プランのセキュリティ保護Microsoft 365 [10 の方法](../security-and-compliance/secure-your-business-data.md)