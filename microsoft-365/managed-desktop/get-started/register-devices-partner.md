---
title: デバイスを登録するためのパートナー向け手順
description: Microsoft Managed Desktop でデバイスを管理できるよう、パートナーがデバイスを登録する方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: baf15ca4b83052af84d2b22b3d2604c6022ac900
ms.sourcegitcommit: 39609c4d8c432c8e7d7a31cb35c8020e5207385b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2021
ms.locfileid: "51445592"
---
# <a name="steps-for-partners-to-register-devices"></a>デバイスを登録するためのパートナー向け手順


このトピックでは、パートナーがデバイスを登録するための手順について説明します。 デバイスを自分で登録するプロセスについては、「Microsoft Managed Desktop のデバイスを自分で登録する [」に記載されています](register-devices-self.md)。



## <a name="prepare-for-registration"></a>登録の準備 
顧客の登録を完了する前に、まずパートナー センターで顧客との関係を [確立する必要があります](https://partner.microsoft.com/dashboard)。 そのプロセスの [詳細については、](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) 同意のドキュメントを参照してください。 CSP パートナーは、お客様の同意がある限り、任意の顧客に代わってデバイスを追加できます。 パートナーの関係と自動操縦のアクセス許可の詳細については、「パートナー センター [のヘルプ」を参照してください](/partner-center/customers_revoke_admin_privileges#windows-autopilot)。


> [!NOTE]
> このドキュメントは、パートナーと OEM 専用です。 自己登録のプロセスについては、「Microsoft Managed Desktop のデバイスを自分で登録 [する」に記載されています](register-devices-self.md)。


## <a name="register-devices-by-using-partner-center"></a>パートナー センターを使用してデバイスを登録する

顧客との関係を確立したら、パートナー センターを利用して、次の手順に従って、関係のある顧客のデバイスを Autopilot に追加できます。

1. パートナー センター [に移動する](https://partner.microsoft.com/dashboard)
2. [ **パートナー センター** ] メニューから [顧客] を選択し、管理するデバイスを持つ顧客を選択します。
3. 顧客の詳細ページで、[デバイス] を **選択します**。
4. [デバイス **にプロファイルを適用する]** で、[デバイスの追加 **] を選択します**。
5. グループ **Microsoft365Managed_Autopilot** を入力し、[参照] を選択して顧客のリスト (.csv ファイル形式) をパートナー センターにアップロードします。


> [!IMPORTANT]
> グループ名は大文字と特殊文字 **Microsoft365Managed_Autopilot** 完全に一致する必要があります。 これにより、新しく登録されたデバイスに Microsoft Managed Desktop Autopilot プロファイルを割り当てることができます。

>[!NOTE]
> デバイスの購入でこの .csv ファイルを受け取っている必要があります。 .csv ファイルを受信しなかった場合は [、「Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)へのデバイスの追加」の手順に従って、自分で作成できます。 このWindows PowerShellは [、Microsoft Managed Desktop Admin](./register-devices-self.md?view=o365-worldwide#obtain-the-hardware-hash)ポータルで使用されるスクリプトとは異なります。 パートナーは [、Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) を使用して、Microsoft マネージ デスクトップ デバイスのデバイスをパートナー センターに登録する必要があります。

.csv ファイルのアップロード中にエラー メッセージが表示される場合は、ファイルの形式を確認します。 列の順序が「新しいデバイスで [Windows Autopilot](/partner-center/autopilot#add-devices-to-a-customers-account)プロファイルを使用して顧客のアウトボックス エクスペリエンスをカスタマイズする」で説明されている順序と一致するようにします。 [デバイスの追加] の横にあるリンクから提供されるサンプルの .csv ファイルを使用 **して、デバイス** リストを作成することもできます。 

パートナー シナリオでの自動パイロットの詳細については、「デバイスを [顧客のアカウントに追加する」を参照してください](/partner-center/autopilot#add-devices-to-a-customers-account)。


## <a name="register-devices-by-using-the-oem-api"></a>OEM API を使用してデバイスを登録する

顧客の登録を完了する前に、まず顧客との関係を確立する必要があります。 それぞれの顧客に提供する一意のリンクが必要です。 「OEM [リレーションシップを確立する方法」を参照してください](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。

リレーションシップを確立したら、グループ タグ を使用して顧客のデバイスの登録を開始 **Microsoft365Managed_Autopilot。**

> [!IMPORTANT]
> グループ名は大文字と特殊文字 **Microsoft365Managed_Autopilot** 完全に一致する必要があります。 これにより、新しく登録されたデバイスに Microsoft Managed Desktop Autopilot プロファイルを割り当てることができます。