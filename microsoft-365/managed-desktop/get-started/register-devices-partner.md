---
title: デバイスを登録するためのパートナー向け手順
description: Microsoft Managed Desktop でデバイスを管理できるよう、パートナーがデバイスを登録する方法
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
ms.openlocfilehash: 227786fdcf1e490be1e3ce74bbc1be1c5f21acfe
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689235"
---
# <a name="steps-for-partners-to-register-devices"></a>デバイスを登録するためのパートナー向け手順


この記事では、パートナーがデバイスを登録するための手順について説明します。 デバイスを自分で登録するプロセスについては、「Microsoft Managed Desktop のデバイスを自分で登録する [」に記載されています](register-devices-self.md)。



## <a name="prepare-for-registration"></a>登録の準備 
顧客の登録を完了する前に、まずパートナー センターで顧客との関係を [確立する必要があります](https://partner.microsoft.com/dashboard)。 そのプロセスの [詳細については、](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) 同意のドキュメントを参照してください。 CSP パートナーは、お客様の同意がある限り、任意の顧客に代わってデバイスを追加できます。 パートナーの関係と自動操縦のアクセス許可の詳細については、「パートナー センター [のヘルプ」を参照してください](/partner-center/customers_revoke_admin_privileges#windows-autopilot)。


> [!NOTE]
> このドキュメントは、パートナーと OEM 専用です。 自己登録のプロセスについては、「Microsoft Managed Desktop のデバイスを自分で登録 [する」に記載されています](register-devices-self.md)。


## <a name="register-devices-by-using-partner-center"></a>パートナー センターを使用してデバイスを登録する

顧客との関係を確立したら、パートナー センターを使用して、次の手順に従って、関係のある顧客のデバイスを Autopilot に追加できます。

1. パートナー センター [に移動する](https://partner.microsoft.com/dashboard)
2. [ **パートナー センター** ] メニューから [顧客] を選択し、管理するデバイスを持つ顧客を選択します。
3. 顧客の詳細ページで、[デバイス] を **選択します**。
4. [デバイス **にプロファイルを適用する]** で、[デバイスの追加 **] を選択します**。
5. 次の表に示すように、選択したデバイス プロファイルに適切なグループ タグを入力し、[参照]を選択して顧客のリスト (.csv ファイル形式) をパートナー センターにアップロードします。

|[デバイス プロファイル](../service-description/profiles.md)  |グループ タグ  |
|---------|---------|
|機密性の高いデータ     |**Microsoft365Managed \_ SensitiveData**    |
|Power User     | **Microsoft365Managed \_ PowerUser**          |
|標準     | **Microsoft365Managed \_ Standard**        |

> [!IMPORTANT]
> グループ名は、大文字と特殊文字を含む、表に記載されている名前と完全に一致する必要があります。 これにより、新しく登録されたデバイスに Microsoft Managed Desktop Autopilot プロファイルを割り当てることができます。

>[!NOTE]
> デバイスの購入時にこの.csvファイルを受け取っている必要があります。 ファイルを受け取らなかった [.csv、Windows Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)にデバイスを追加するの手順に従って、自分で作成できます。 このWindows PowerShellは [、Microsoft Managed Desktop Admin](./register-devices-self.md#obtain-the-hardware-hash)ポータルで使用されるスクリプトとは異なります。 パートナーは [、Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) を使用して、Microsoft マネージ デスクトップ デバイスのデバイスをパートナー センターに登録する必要があります。

ファイルのアップロード中にエラー メッセージが表示.csvファイルの形式を確認します。 列の順序が「新しいデバイスで [Windows Autopilot](/partner-center/autopilot#add-devices-to-a-customers-account)プロファイルを使用して顧客のアウトボックス エクスペリエンスをカスタマイズする」で説明されている順序と一致するようにします。 [デバイスの追加] の横にあるリンク.csvサンプル ファイルを使用して、デバイス リストを作成することもできます。 

パートナー シナリオでの自動パイロットの詳細については、「デバイスを [顧客のアカウントに追加する」を参照してください](/partner-center/autopilot#add-devices-to-a-customers-account)。


## <a name="register-devices-by-using-the-oem-api"></a>OEM API を使用してデバイスを登録する

顧客の登録を完了する前に、まず顧客との関係を確立する必要があります。 それぞれの顧客に提供する一意のリンクが必要です。 「OEM [リレーションシップを確立する方法」を参照してください](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。

リレーションシップを確立したら、選択したデバイス プロファイルごとに適切なグループ タグを使用して、顧客のデバイスの登録を開始できます。


|デバイス プロファイル  |グループ タグ  |
|---------|---------|
|機密性の高いデータ     | **Microsoft365Managed \_ SensitiveData**     |
|Power User     | **Microsoft365Managed \_ PowerUser**          |
|標準     | **Microsoft365Managed \_ Standard**      |

> [!IMPORTANT]
> グループ タグは、大文字と特殊文字を含む、表に記載されているタグと完全に一致する必要があります。 これにより、新しく登録されたデバイスに Microsoft Managed Desktop Autopilot プロファイルを割り当てることができます。