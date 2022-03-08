---
title: パートナーの登録
description: パートナーは、Microsoft Managed Desktop によって管理されるデバイスを登録できます。
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: af1e187c77acde257fa3458709fae50616cf810d
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330966"
---
# <a name="partner-registration"></a>パートナーの登録

この記事では、パートナーがデバイスを登録する手順について説明します。 デバイスを自分で登録するプロセスについては、「手動登録」 [に記載されています](manual-registration.md)。

## <a name="prepare-for-registration"></a>登録の準備

顧客の登録を完了する前に、まずパートナー センターで顧客との関係を [確立する必要があります](https://partner.microsoft.com/dashboard)。 そのプロセスの詳細については、同意に関するドキュメントを [参照してください](/windows/deployment/windows-autopilot/registration-auth#csp-authorization)。 CSP パートナーは、お客様の同意がある限り、任意の顧客に代わってデバイスを追加できます。 パートナーとの関係と自動操縦のアクセス許可の詳細については、パートナー センター [のヘルプを参照してください](/partner-center/customers_revoke_admin_privileges#windows-autopilot)。

> [!NOTE]
> このドキュメントは、パートナーと OEM 専用です。 自己登録のプロセスについては、「手動登録」 [に記載されています](manual-registration.md)。

## <a name="register-devices-using-the-partner-center"></a>パートナー センターを使用してデバイスを登録する

顧客との関係を確立したら、パートナー センターを使用して、任意の顧客のデバイスを Autopilot に追加できます。

**パートナー センターを使用してデバイスを登録するには、次のコマンドを実行します。**

1. [パートナー センター [] に移動します](https://partner.microsoft.com/dashboard)。
2. [ **パートナー センター** ] メニューから [顧客] を選択し、管理するデバイスを持つ顧客を選択します。
3. 顧客の詳細ページで、[デバイス] を **選択します**。
4. [デバイス **にプロファイルを適用する** ] で、[デバイスの **追加] を選択します**。
5. 次の表に示すように、選択したデバイス プロファイルに適切なグループ タグを入力し、[参照] を選択して顧客のリスト (.csv ファイル形式) をパートナー センターにアップロードします。

| [デバイス プロファイル](../service-description/profiles.md) | グループ タグ |
| ----- | -----|
| 機密性の高いデータ | **Microsoft365ManagedSensitiveData\_** |
| Power User | **Microsoft365ManagedPowerUser\_** |
| Standard | **Microsoft365ManagedStandard\_** |

> [!IMPORTANT]
> グループ名は、大文字と特殊文字を含む、表に記載されている名前と完全に一致する必要があります。 これにより、新しく登録されたデバイスに Microsoft Managed Desktop Autopilot プロファイルを割り当てることができます。

>[!NOTE]
> デバイスの購入時にこの.csvファイルを受け取っている必要があります。 ファイルを受け取らなかった場合.csv、[Autopilot](/windows/deployment/windows-autopilot/add-devices#collecting-the-hardware-id-from-existing-devices-using-powershell) にデバイスを追加するの手順に従って、Windowsできます。 要件: <ul><li>追加の列はサポートされていません。</li> <li>引用符はサポートされていません。</li> <li>ANSI 形式のテキスト ファイルのみを使用できます (Unicode は使用できません)。</li> <li>ヘッダーでは大文字と小文字が区別されます。</li></ul> ファイルを CSV ファイルExcel編集して CSV ファイルとして保存すると、これらの要件のために使用できるファイルは生成されない。 デバイスのシリアル番号の先頭に 0 が残っている必要があります。 パートナーは [、Get-WindowsAutoPilotInfo](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) を使用して、Microsoft マネージ デスクトップ デバイスのデバイスをパートナー センターに登録する必要があります。

ファイルのアップロード中にエラー メッセージが表示.csvファイルの形式を確認します。 列の順序が、「新しいデバイスで自動操縦プロファイルWindows使用して顧客のアウトボックス エクスペリエンスをカスタマイズする」で説明されている順序と一致するように[します](/partner-center/autopilot#add-devices-to-a-customers-account)。 [デバイスの追加] の横にあるリンク.csvサンプル ファイルを使用して、デバイスリストを作成することもできます。

パートナー シナリオでの自動操縦の詳細については、「デバイスを顧客のアカウントに追加 [する」を参照してください](/partner-center/autopilot#add-devices-to-a-customers-account)。

## <a name="register-devices-by-using-the-oem-api"></a>OEM API を使用してデバイスを登録する

顧客の登録を完了する前に、まず顧客との関係を確立する必要があります。 それぞれの顧客に提供する一意のリンクが必要です。 「 [OEM 関係を確立する方法」を参照してください](/windows/deployment/windows-autopilot/registration-auth#oem-authorization)。

リレーションシップを確立したら、選択したデバイス プロファイルごとに適切なグループ タグを使用して、顧客のデバイスの登録を開始できます。

| デバイス プロファイル | グループ タグ |
| ----- | ----- |
| 機密性の高いデータ | **Microsoft365ManagedSensitiveData\_** |
| Power User | **Microsoft365ManagedPowerUser\_** |
| Standard | **Microsoft365ManagedStandard\_** |

> [!IMPORTANT]
> グループ タグは、大文字と特殊文字を含む、表に記載されているタグと完全に一致する必要があります。 これにより、新しく登録されたデバイスに Microsoft Managed Desktop Autopilot プロファイルを割り当てることができます。
