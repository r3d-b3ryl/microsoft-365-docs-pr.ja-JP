---
title: デバイスを登録するためのパートナー向け手順
description: パートナーがデバイスを登録して、デバイスをユーザーが管理Microsoft マネージド デスクトップ
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 2849857b2196a863c236352ca4c7fd3c0dda1e6f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211491"
---
# <a name="steps-for-partners-to-register-devices"></a>デバイスを登録するためのパートナー向け手順


この記事では、パートナーがデバイスを登録するための手順について説明します。 デバイスを自分で登録するプロセスについては、「デバイスを自分で登録[する」にMicrosoft マネージド デスクトップ記載されています](register-devices-self.md)。



## <a name="prepare-for-registration"></a>登録の準備 
顧客の登録を完了する前に、まずパートナー センターで顧客との関係を [確立する必要があります](https://partner.microsoft.com/dashboard)。 そのプロセスの [詳細については、](/windows/deployment/windows-autopilot/registration-auth#csp-authorization) 同意のドキュメントを参照してください。 CSP パートナーは、お客様の同意がある限り、任意の顧客に代わってデバイスを追加できます。 パートナーの関係と自動操縦のアクセス許可の詳細については、「パートナー センター [のヘルプ」を参照してください](/partner-center/customers_revoke_admin_privileges#windows-autopilot)。


> [!NOTE]
> このドキュメントは、パートナーと OEM 専用です。 自己登録のプロセスについては、「デバイスを自分で登録[する」にMicrosoft マネージド デスクトップ記載されています](register-devices-self.md)。


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
|Standard     | **Microsoft365Managed \_ Standard**        |

> [!IMPORTANT]
> グループ名は、大文字と特殊文字を含む、表に記載されている名前と完全に一致する必要があります。 これにより、新しく登録されたデバイスに Autopilot プロファイルMicrosoft マネージド デスクトップ割り当てることができます。

>[!NOTE]
> デバイスの購入時にこの.csvファイルを受け取っている必要があります。 ファイルを受け取らなかった.csv、Autopilot にデバイスを追加するの手順に従って[、Windows作成できます](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell)。 追加の列はサポートされていません。 引用符はサポートされていません。 ANSI 形式のテキスト ファイルのみを使用できます (Unicode は使用できません)。 ヘッダーでは大文字と小文字が区別されます。 これらの要件のために、Excelを編集して CSV ファイルとして保存すると、使用できるファイルは生成できません。 デバイスのシリアル番号の先頭に 0 が残っている必要があります。 パートナーは[、Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo)を使用して、パートナー センターでデバイスMicrosoft マネージド デスクトップデバイスを登録する必要があります。

ファイルのアップロード中にエラー メッセージが表示.csvファイルの形式を確認します。 列の順序が、「新しいデバイスで自動操縦プロファイルWindows使用して顧客のアウトボックス エクスペリエンスをカスタマイズする」で説明されている順序と一致するように[します](/partner-center/autopilot#add-devices-to-a-customers-account)。 [デバイスの追加] の横にあるリンク.csvサンプル ファイルを使用して、デバイス リストを作成することもできます。 

パートナー シナリオでの自動パイロットの詳細については、「デバイスを [顧客のアカウントに追加する」を参照してください](/partner-center/autopilot#add-devices-to-a-customers-account)。


## <a name="register-devices-by-using-the-oem-api"></a>OEM API を使用してデバイスを登録する

顧客の登録を完了する前に、まず顧客との関係を確立する必要があります。 それぞれの顧客に提供する一意のリンクが必要です。 「OEM [リレーションシップを確立する方法」を参照してください](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。

リレーションシップを確立したら、選択したデバイス プロファイルごとに適切なグループ タグを使用して、顧客のデバイスの登録を開始できます。


|デバイス プロファイル  |グループ タグ  |
|---------|---------|
|機密性の高いデータ     | **Microsoft365Managed \_ SensitiveData**     |
|Power User     | **Microsoft365Managed \_ PowerUser**          |
|Standard     | **Microsoft365Managed \_ Standard**      |

> [!IMPORTANT]
> グループ タグは、大文字と特殊文字を含む、表に記載されているタグと完全に一致する必要があります。 これにより、新しく登録されたデバイスに Autopilot プロファイルMicrosoft マネージド デスクトップ割り当てることができます。
