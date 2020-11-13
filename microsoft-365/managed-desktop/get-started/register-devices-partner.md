---
title: デバイスを登録するためのパートナー向け手順
description: パートナーが Microsoft マネージドデスクトップで管理できるようにデバイスを登録する方法
ms.prod: w10
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.openlocfilehash: 7e40a5eb7144fef3d330e0e8fc3c711af15d4c49
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071445"
---
# <a name="steps-for-partners-to-register-devices"></a>デバイスを登録するためのパートナー向け手順


このトピックでは、パートナーがデバイスを登録するために従う必要のある手順について説明します。 自分でデバイスを登録するプロセスについては、「 [Microsoft マネージドデスクトップの登録デバイス](register-devices-self.md)」に記載されています。



## <a name="prepare-for-registration"></a>登録の準備 
お客様の登録を完了する前に、 [パートナーセンター](https://partner.microsoft.com/dashboard)で、お客様との関係を確立する必要があります。 そのプロセスの詳細については、 [同意書](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#csp-authorization) を参照してください。 すべての CSP パートナーは、お客様が同意する限り、お客様の代わりにデバイスを追加できます。 パートナー関係および自動操縦のアクセス許可の詳細については、 [パートナーセンターのヘルプ](https://docs.microsoft.com/partner-center/customers_revoke_admin_privileges#windows-autopilot)を参照してください。


> [!NOTE]
> このドキュメントは、パートナーと Oem のみを対象としています。 自己登録のプロセスについては、「 [Microsoft マネージドデスクトップの登録デバイス](register-devices-self.md)」に記載されています。


## <a name="register-devices-by-using-partner-center"></a>パートナーセンターを使用してデバイスを登録する

お客様との関係を確立したら、次の手順に従って、パートナーセンターを活用して、関係のあるお客様のためにデバイスを自動操縦に追加できます。

1. [パートナーセンター](https://partner.microsoft.com/dashboard)への移動
2. パートナーセンターメニューから [ **顧客** ] を選択し、管理するデバイスのお客様を選択します。
3. お客様の詳細ページで、[ **デバイス** ] を選択します。
4. [デバイスへの **プロファイルの適用** ] で、[ **デバイスの追加** ] を選択します。
5. グループ名の **Microsoft365Managed_Autopilot** を入力し、[ **参照** ] を選択して、顧客のリスト (.csv ファイル形式) をパートナーセンターにアップロードします。


> [!IMPORTANT]
> グループ名は、大文字と小文字を区別し **Microsoft365Managed_Autopilot** 正確に一致する必要があります。 これにより、新しく登録されたデバイスを Microsoft Managed Desktop 自動操縦プロファイルに割り当てることができます。

>[!NOTE]
> この .csv ファイルは、デバイスの購入時に入手する必要があります。 .Csv ファイルを受け取っていない場合は、「 [Windows 自動操縦にデバイスを追加する](https://docs.microsoft.com/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)」の手順に従って作成します。 Windows PowerShell スクリプトは、 [Microsoft Managed Desktop 管理ポータル](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/register-devices-self?view=o365-worldwide#obtain-the-hardware-hash)で使用されているものとは異なります。 パートナーは [、g-et-windowsautopilotinfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) を使用してパートナーセンターの Microsoft マネージドデスクトップデバイスにデバイスを登録する必要があります。

.Csv ファイルのアップロード中にエラーメッセージが表示される場合は、ファイルの形式を確認してください。 「 [新しいデバイスで Windows 自動操縦プロファイルを使用する](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)」で説明されている内容と一致していることを確認して、お客様の標準外の環境をカスタマイズします。 次のリンクから提供されているサンプル .csv ファイルを使用して、[デバイスの **追加** ] リストを作成することもできます。 

パートナーシナリオでの自動操縦の詳細については、「 [顧客のアカウントにデバイスを追加する](https://docs.microsoft.com/partner-center/autopilot#add-devices-to-a-customers-account)」を参照してください。


## <a name="register-devices-by-using-the-oem-api"></a>OEM API を使用してデバイスを登録する

顧客の登録を完了する前に、顧客との関係を確立する必要があります。 それぞれの顧客に提供する固有のリンクを用意する必要があります。 「 [OEM の関係を確立する方法」を](https://docs.microsoft.com/windows/deployment/windows-autopilot/registration-auth#oem-authorization)参照してください。

関係を確立したら、グループタグ **Microsoft365Managed_Autopilot** を使用して、顧客用のデバイスの登録を開始できます。

> [!IMPORTANT]
> グループ名は、大文字と小文字を区別し **Microsoft365Managed_Autopilot** 正確に一致する必要があります。 これにより、新しく登録されたデバイスを Microsoft Managed Desktop 自動操縦プロファイルに割り当てることができます。
