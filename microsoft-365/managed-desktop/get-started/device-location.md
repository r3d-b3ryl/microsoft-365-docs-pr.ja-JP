---
title: Windows 10 の位置情報サービス
description: デバイスの位置情報Windowsを有効にする方法
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
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
ms.openlocfilehash: 546b436b4090b060e03794455de1b1edd5eae2b9
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035548"
---
# <a name="windows-10-location-service"></a>Windows 10 の位置情報サービス

Microsoft Managed Desktop のデバイスは、自動パイロットを使用してWindowsされます。 このプロセスでは、ユーザーとユーザーのAzure Active Directory管理Microsoft Intune。 既定では、Windows 10が初めて有効になっている場合、この機能が "箱から出た" エクスペリエンス中にプライバシー設定で有効になっていない限り、Windows 10 位置情報サービスは無効になっています。 これらの設定は、Microsoft Managed Desktop での自動パイロット登録中に非表示になります。 Autopilot のセットアップ方法の詳細については、「Autopilot での初回実行エクスペリエンス」および「登録状態ページ」 [を参照してください](esp-first-run.md)。

このため、Microsoft Managed Desktop デバイスはデバイスの場所を取得できません。これにより、タイム ゾーンなどの複数の機能Windows制限されます。 位置情報サービスの詳細についてはWindows 10位置情報サービスとWindows 10[を参照してください](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。

Microsoft Managed Desktop に参加するために位置情報サービスを使用する必要は一方で、ユーザー エクスペリエンスは制限されます。 たとえば、デバイスは、ユーザーが別のタイム ゾーンで作業するときに、自分のタイムゾーンを自動的に判断できません。

## <a name="enable-the-location-service"></a>位置情報サービスを有効にする

デバイスを Microsoft Managed Desktop サービスに登録するときに、位置情報サービスの使用をオプトインするか、登録後にサービスをオンまたはオフにできます。

### <a name="opt-in-during-enrollment"></a>登録中にオプトインする

Microsoft Managed Desktop サービスで位置情報サービスを有効にできます。 登録シーケンス中に、デバイスで位置情報サービスを有効にするかどうかを選択Windows 10求めるメッセージが表示されます。

### <a name="control-the-location-service-after-enrollment"></a>登録後に位置情報サービスを制御する

管理ポータルからサポート要求を送信することで、いつでも位置情報サービスを有効 (または無効) [](../working-with-managed-desktop/admin-support.md) [にできます](access-admin-portal.md)。

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a>Microsoft Managed Desktop が位置情報サービスWindows 10構成する方法

位置情報サービスの使用をオプトインする場合、ユーザーのプライバシーに影響を与えることなく、必要な最小設定を使用します。 詳細については、「位置情報サービス[Windows 10プライバシー」を参照してください](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。

Microsoft Managed Desktop では、[このデバイスの **場所** へのアクセスWindows **を** 許可する] に設定されている場所 **のプライバシー設定を有効にします**。 ユーザー インターフェイスは次のように表示されます。

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="[場所の設定] Windows設定します。":::

> [!NOTE]
> 位置情報サービスの使用をオプトインする場合、これはオペレーティング システム自体Windows適用されます。 アプリは位置情報サービスを使用することはできません。 各ユーザーは、アプリが自分の場所にアクセスできるかどうかを選択できます。