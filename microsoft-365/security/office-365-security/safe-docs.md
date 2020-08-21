---
title: Office 365 ATP の安全なドキュメント
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Microsoft 365 E5 または Microsoft 365 E5 Security の安全なドキュメントについて説明します。
ms.openlocfilehash: cd689099fc6a6caa1e0e649c3f152f1de123bf12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827471"
---
# <a name="safe-documents-in-microsoft-365-e5"></a>Microsoft 365 E5 の安全なドキュメント

安全なドキュメントは、Microsoft 365 E5 または Microsoft 365 E5 セキュリティの機能です。 [この機能は、保護](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) ビューで開かれていたドキュメントやファイルを Microsoft Defender Advanced Threat Protection [を使用してスキャンします](https://support.microsoft.com/office/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- 安全なドキュメントは、通常、Office バージョン 2004 (12730.x) 以上のユーザーから入手可能になります。 この機能は既定でオフになっており、セキュリティ管理者が有効にする必要があります。

- この機能は *、Microsoft 365 E5 または Microsoft 365* E5 セキュリティ ライセンス (Office *365* ATP プランには含まれていません) を持つユーザーのみが利用できます。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- このトピックの手順を実行する場合は、あかじにアクセス許可を割り当てる必要があります。 安全なドキュメントを有効にして構成するには、組織の管理役割グループまたは **セキュリティ管理者役割グループ** の **メンバーである** 必要があります。 セキュリティ/コンプライアンス センターの役割グループの詳細については、「[セキュリティ/コンプライアンス センターでのアクセス許可](permissions-in-the-security-and-compliance-center.md)」をご覧ください。

## <a name="how-does-microsoft-handle-your-data"></a>Microsoft はおデータをどのように処理しますか?

保護された安全なドキュメントは、Microsoft Defender Advanced [Threat Protection クラウドに分析用に](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) ファイルを送信します。

- Microsoft Defender Advanced Threat Protection によるデータの処理方法について詳しくは、こちらを参照 [してください。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)
- 上記のガイドラインに加えて、「安全なドキュメントから送信されたファイル」は、通常、24 時間未満の時間を超えて Defender に保持されません。

## <a name="use-the-security--compliance-center-to-configure-safe-documents"></a>セキュリティ コンプライアンス センターを&を使用して安全なドキュメントを構成する

1. [監視] & [インストール] を開きます <https://protection.office.com> 。

2. 脅威管理**ポリシー** \> **Policy** \> **の ATP の安全な添付ファイルに移動します**。

3. [Office **アプリケーションの保護ビュー] セクションの保護ビュー以外ではファイルを開くことがファイルを信頼しても安全な状態を保つため、次** のどちらかの設定を構成します。

   - **アクセス クライアントの「安全なドキュメント」Officeオンにする**

   - **「安全なドキュメント」が悪意のあるファイルとして**識別されている場合でも、保護ビューでのユーザーのクリックを許可します。 このオプションは有効にしないでください。

4. 完了したら、**[保存]** をクリックします。

![ATP の安全な添付ファイル ページ](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-documents"></a>Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用して安全なドキュメントを構成する

次の構文を使用してください。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true | $false> -AllowSafeDocsOpen <$true | $false>
```

- _EnableSafeDocs パラメーターは_、組織全体の安全なドキュメントを有効または無効にします。

- _AllowSafeDocsOpen パラメーターを_指定すると、ユーザーが保護ビューを開く操作 (つまり、ドキュメントを開く) を禁止するかどうかを指定できます (ドキュメントは、悪意があると特定された場合)。

この例では、組織全体に対して安全なドキュメントを有効にし、ユーザーが悪意のあることが特定されたドキュメントを保護ビューから開くことがないようにします。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

構文およびパラメーターの詳細については [、「Set-AtpPolicyForO365」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-atppolicyforo365)。

### <a name="how-do-i-know-this-worked"></a>設定が適用されたことを確認する方法

安全なドキュメントの有効化と構成が完了したことを確認するには、次のいずれかの手順を実行します。

- セキュリティ & コンプライアンス センターでは、脅 **威管理** \> **ポリシー** \> **ATP の安全な添付ファイル**に移動し、ファイルが信頼して Office アプリケーションの保護ビュー セクション以外で開くときも、ヘルプユーザーが安全 **に選択した内容を保管します** 。

- Exchange Online PowerShell で次のコマンドを実行し、プロパティの値を確認します。

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
