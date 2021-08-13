---
title: AutoPilot デバイス エラーのトラブルシューティング
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: このページで AutoPilot デバイス ファイルを操作している間に表示される可能性のあるエラーのトラブルシューティングMicrosoft 365 Business Premium。
ms.openlocfilehash: b74c57acbaa5682f6db97e7d8a090e6e28a40dcc3246f00cacc7984cb52cc758
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53809182"
---
# <a name="troubleshoot-autopilot-device-errors"></a>AutoPilot デバイス エラーのトラブルシューティング

## <a name="device-file-error-messages"></a>デバイス ファイルのエラー メッセージ

このページでは、AutoPilot デバイス ファイルの操作中に表示されるエラーの一部についてMicrosoft 365 Business Premium。 
  
|**エラー コード**|**試してみる修正**|
|:-----|:-----|
|要求本文が無効です  <br/> |このエラーはまれに発生します。このエラーが表示された場合は、もう一度操作を試してください。  <br/> |
|デバイスのハードウェア ハッシュ値が正しくありません。  <br/> |このエラーが表示された場合は、1 つのデバイスのハードウェア ハッシュに対して CSV ファイルに指定した値が正しくありません。 最初に、値が正しく入力されていることを確認します。 値が正しいと思うが、このエラーがまだ発生している場合は、ハードウェア ベンダーに問い合わせください。  <br/> |
|別のテナントに割り当てられたデバイス  <br/> |このエラーが表示された場合は、1 つ以上のデバイスのシリアル番号またはプロダクト キーに対して CSV ファイルに指定した値が正しくありません。 最初に、値が正しく入力されていることを確認します。 値が正しいと思うが、このエラーがまだ発生している場合は、ハードウェア ベンダーに問い合わせください。  <br/> |
|CSV ファイルに無効なシリアル番号またはプロダクト キーが含まれている  <br/> |このエラーが表示された場合は、登録しようとしているデバイスが別の組織によって既に登録されているという意味です。 このエラーを修正するには、ハードウェア ベンダーにヘルプを求める必要があります。  <br/> |
|このデバイスは、AutoPilot を使用したセットアップではサポートされていません  <br/> | このエラーは、デバイスが AutoPilot の展開要件を満たしていることを意味します。 デバイスは次の要件を満たしている必要があります。  <br/>  Windows 10 バージョン 1703 以降。  <br/>  使用されていない新しいデバイスWindowsエクスペリエンスを提供します。  <br/> |
|デバイスが見つかりません  <br/> |このエラーは、CSV ファイル内の 1 つ以上のデバイスが組織に登録されていないことを意味します。 これを修正するには、ハードウェア ベンダーにヘルプを求める必要があります。  <br/> |
