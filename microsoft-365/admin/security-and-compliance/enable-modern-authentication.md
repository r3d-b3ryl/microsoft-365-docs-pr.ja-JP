---
title: Windows デバイスの Office 2013 の先進認証を有効にする
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 7dc1c01a-090f-4971-9677-f1b192d6c910
description: Microsoft Office 2013 がインストールされているデバイスの最新の認証を有効にするレジストリ キーの設定方法を説明します。
ms.openlocfilehash: f1264affa5be93b19e564a0edea00bfb78f452f1
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/24/2020
ms.locfileid: "42248003"
---
# <a name="enable-modern-authentication-for-office-2013-on-windows-devices"></a>Windows デバイスの Office 2013 の先進認証を有効にする

Office 2013 がインストールされている Windows デバイスで先進認証を有効にするには、特定のレジストリ キーを設定する必要があります。
  
## <a name="enable-modern-authentication-for-office-2013-clients"></a>Office 2013 クライアントの先進認証を有効にする

> [!NOTE]
> 先進認証は Office 2016 クライアントで既に有効になっているため、Office 2016 のレジストリ キーを設定する必要はありません。 
  
Microsoft Office 2013 がインストールされている Windows を実行しているデバイス (たとえばノート PC やタブレット) で先進認証を有効にするには、次のレジストリ キーを設定する必要があります。先進認証を有効にするデバイスごとに、次のキーを設定する必要があります。
  
|**レジストリ キー**|**型**|**値** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
   
レジストリ キーを設定したら、Office 365 で[多要素認証 (MFA)](set-up-multi-factor-authentication.md) を使用するように Office 2013 デバイス アプリを設定できます。 
  
現在、クライアント アプリのいずれかを使ってサインインしている場合、変更を有効にするには、サインアウトしてサインインし直す必要があります。それ以外の場合は、ADAL ID が確立されるまで、MRU とローミングの設定が無効になります。
  
## <a name="disable-modern-authentication-on-devices"></a>デバイスで先進認証を無効にする

デバイスで先進認証を無効にするには、デバイスで次のレジストリ キーを設定します。
  
|**レジストリ キー**|**型**|**値**|
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL |REG_DWORD|0|
   
## <a name="related-articles"></a>関連記事
[第 2 検証方法を使用して Office 2013 にサインインする](https://support.office.com/article/2b856342-170a-438e-9a4f-3c092394d3cb.aspx)

  

