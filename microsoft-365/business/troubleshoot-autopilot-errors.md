---
title: 自動操縦デバイス エラーをトラブルシューティングする
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: 自動操縦装置のデバイス ファイルのエラーをトラブルシューティングする方法について説明します。
ms.openlocfilehash: 9b8d8ab424dd3189ff5c228dab8f5c513ff5dafc
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869179"
---
# <a name="troubleshoot-autopilot-device-errors"></a>自動操縦デバイス エラーをトラブルシューティングする

## <a name="device-file-error-messages"></a>デバイス ファイルのエラー メッセージ

エラーのいくつかのここでの情報表示されるマイクロソフト 365 ビジネス内のデバイス ファイルの自動操縦装置の操作中にあります。 
  
|**エラー コード**|**しようとする修正プログラム**|
|:-----|:-----|
|無効な要求の本体  <br/> |まれには、このエラーが発生このエラーが発生した場合、もう一度やり直してください。  <br/> |
|デバイスのハードウェア ハッシュの値が正しくないです。  <br/> |このエラーが表示された場合は、1 つのデバイスのハードウェア ハッシュの CSV ファイルで指定した値が正しくないことを意味します。最初に、値が正しく入力されているを確認します。値は正しいですが、このエラーが引き続き発生している場合は、ヘルプについては、ハードウェアの製造元に問い合わせてください。  <br/> |
|他のテナントに割り当てられたデバイス  <br/> |このエラーが表示された場合は、シリアル番号または 1 つまたは複数のデバイスのプロダクト キーのいずれかの CSV ファイルで指定された値が正しくないことを意味します。最初に、値が正しく入力されているを確認します。値は正しいですが、このエラーが引き続き発生している場合は、ヘルプについては、ハードウェアの製造元に問い合わせてください。  <br/> |
|CSV ファイルには、無効なシリアル番号、またはプロダクト キーが含まれています。  <br/> |このエラーが発生する場合は、他の組織で登録しようとしたときのデバイスが既に登録されていることを意味します。これを修正するには、ヘルプについては、ハードウェアの製造元に問い合わせてください。  <br/> |
|このデバイスが自動操縦を使用して、セットアップでサポートされていません  <br/> | このエラーは、デバイスが自動操縦装置の配置の要件を満たしていないを意味します。デバイスは、これらの要件を満たす必要があります。  <br/>  Windows 10 バージョン 1703 以降。  <br/>  Windows out-of-box experience を行っていない新しいデバイス。  <br/> |
|装置が見つかりません。  <br/> |このエラーは、CSV ファイル内の 1 つまたは複数のデバイスが組織に登録されていないことを意味します。これを修正するには、ヘルプについては、ハードウェアの製造元に問い合わせてください。  <br/> |
   
