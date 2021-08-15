---
title: Windows 10 の位置情報サービス
description: デバイスの位置情報Windowsを有効にする方法
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
ms.openlocfilehash: a98f3a4d1bda182331f81de0c0c5cf232940819c864b638fb738ae192ff9cc4f
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53854502"
---
# <a name="windows-10-location-service"></a>Windows 10 の位置情報サービス

デバイスはMicrosoft マネージド デスクトップ自動パイロットを使用Windowsされます。 このプロセスでは、ユーザーとユーザーのAzure Active Directory管理Microsoft Intune。 既定では、Windows 10が初めて有効になっている場合、この機能が "箱から出た" エクスペリエンス中にプライバシー設定で有効になっていない限り、Windows 10 位置情報サービスは無効になっています。 これらの設定は、自動パイロット登録時に非表示Microsoft マネージド デスクトップ。 Autopilot のセットアップ方法の詳細については、「Autopilot での初回実行エクスペリエンス」および「登録状態ページ」 [を参照してください](esp-first-run.md)。

このため、Microsoft マネージド デスクトップデバイスはデバイスの場所を取得できません。これにより、タイム ゾーンなどの複数のWindows機能が制限されます。 位置情報サービスの詳細についてはWindows 10位置情報サービスとWindows 10[を参照してください](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。

位置情報サービスを使用してサービスに参加する必要はMicrosoft マネージド デスクトップ、ユーザー エクスペリエンスは制限されます。 たとえば、デバイスは、ユーザーが別のタイム ゾーンで作業するときに、自分のタイムゾーンを自動的に判断できません。

## <a name="enable-the-location-service"></a>位置情報サービスを有効にする

デバイスを Microsoft マネージド デスクトップ サービスに登録するときに、位置情報サービスの使用をオプトインするか、登録後にサービスをオンまたはオフにできます。

### <a name="opt-in-during-enrollment"></a>登録中にオプトインする

位置情報サービスを有効Microsoft マネージド デスクトップサービスを有効にできます。 登録シーケンス中に、デバイスで位置情報サービスを有効にするかどうかを選択Windows 10求めるメッセージが表示されます。

### <a name="control-the-location-service-after-enrollment"></a>登録後に位置情報サービスを制御する

管理ポータルからサポート要求を送信することで、いつでも位置情報サービスを有効 (または無効) [](../working-with-managed-desktop/admin-support.md) [にできます](access-admin-portal.md)。

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a>場所Microsoft マネージド デスクトップサービスを構成するWindows 10方法

位置情報サービスの使用をオプトインする場合、ユーザーのプライバシーに影響を与えることなく、必要な最小設定を使用します。 詳細については、「位置情報サービス[Windows 10プライバシー」を参照してください](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)。

Microsoft マネージド デスクトップ **デバイスの場所** へのアクセスを許可するWindows **設定** で [場所のプライバシー]**設定を有効にします**。 ユーザー インターフェイスは次のように表示されます。

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="[場所の設定] Windows設定":::

> [!NOTE]
> 位置情報サービスの使用をオプトインする場合、これはオペレーティング システム自体Windows適用されます。 アプリは位置情報サービスを使用することはできません。 各ユーザーは、アプリが自分の場所にアクセスできるかどうかを選択できます。