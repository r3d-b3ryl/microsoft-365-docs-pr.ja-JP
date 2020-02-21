---
title: Office 365 ATP の安全なドキュメント
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: kshi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Office 365 ATP の安全なドキュメントについて説明します。
ms.openlocfilehash: 3980746eb2f48e77c22f5139827bead5640dad61
ms.sourcegitcommit: 1c445d68e54ca4249024ca4bb72460dd6fac0a2d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/20/2020
ms.locfileid: "42170477"
---
# <a name="safe-documents-in-office-365-advanced-threat-protection"></a>Office の安全なドキュメント 365 Advanced Threat Protection

「安全なドキュメント」は、 [Microsoft Defender Advanced threat](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection) protection (ATP) を使用して、[保護さ](https://support.office.com/article/d6f09ac7-e6b9-4495-8e43-2bbcdbcb6653)れたビューで開かれたドキュメントやファイルをスキャンする Office 365 advanced threat protection (ATP) の機能です。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- この機能は、Microsoft 365 E5 または Microsoft 365 E5 セキュリティライセンスを持つユーザーのみが使用できます。

- 現在、安全なドキュメントはパブリックプレビューで利用できます。 office [Insider program](https://insider.office.com/en-us/join)の一部であるユーザーが office バージョン 2002 (12527.20092) 以上の ' 月次 Channel (対象指定) ' を使用することができます。 この機能は既定でオフになっており、セキュリティ管理者が有効にする必要があります。

- 現時点では、US 地域のみが準拠しているファイル処理をサポートしています (すべてのファイルは、お客様がスキャンの対象地域に送られます)。 英国/EU 地域のサポートは、今後の更新プログラムで計画されます。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。 Exchange Online Protection PowerShell に接続するには、「 [Exchange Online protection の powershell への接続](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell)」を参照してください。

- このトピックの手順を実行するには、あらかじめアクセス許可を割り当てる必要があります。 安全なドキュメントを有効にして構成するには、組織の**管理**役割グループまたは**セキュリティ管理者**役割グループのメンバーである必要があります。 セキュリティ & コンプライアンスセンターの役割グループの詳細については、「 [Office 365 セキュリティ & コンプライアンスセンターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

## <a name="use-the-office-365-security--compliance-center-to-configure-safe-documents"></a>Office 365 セキュリティ & コンプライアンスセンターを使用して安全なドキュメントを構成する

1. にある<https://protection.office.com>Office 365 セキュリティ & コンプライアンスセンターを開きます。

2. [**脅威管理** \> **ポリシー** \> **ATP 安全な添付ファイル**] に移動します。

3. [ **Office アプリケーションで保護されたビューの外部で開くファイルを信頼する**] セクションで、次のどちらかの設定を構成します。

   - **Office クライアントに対して安全なドキュメントを有効にする (詳細な分析のためにファイルは Microsoft Cloud にも送信されます)**

   - **安全なドキュメントが悪意のあるファイルを識別している場合でも、保護されたビューのクリックをユーザーに許可**します。このオプションは有効にしないことをお勧めします。

4. 完了したら、**[保存]** をクリックします。

![ATP の「安全な添付ファイル」ページ](../../media/safe-docs.png)

### <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-safe-documents"></a>Exchange Online PowerShell または Exchange Online Protection PowerShell を使用して安全なドキュメントを構成する

次の構文を使用してください。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs <$true|$false> -AllowSafeDocsOpen <$true|$false>
```

- _Enablesafedocs_パラメーターは、組織全体に対して安全なドキュメントを有効または無効にします。

- _Allowsafedocsopen_パラメーターを使用すると、ドキュメントが悪意のあるものとして識別された場合に、保護されたビュー (ドキュメントを開く操作) をユーザーが終了できないようにすることができます。

この例では、組織全体に対して安全なドキュメントを有効にし、保護されたビューから悪意があると識別されたドキュメントをユーザーが開くことができないようにします。

```powershell
Set-AtpPolicyForO365 -EnableSafeDocs $true -AllowSafeDocsOpen $false
```

構文およびパラメーターの詳細については、「 [AtpPolicyForO365](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/set-atppolicyforo365)」を参照してください。

### <a name="how-do-i-know-this-worked"></a>設定が適用されたことを確認する方法

安全なドキュメントを有効にして構成したことを確認するには、次のいずれかの手順を実行します。

- [セキュリティ & コンプライアンスセンター] で、[**脅威管理** \> **ポリシー** \> **ATP 安全添付ファイル**] に移動して、[ **Office アプリケーションの外部で保護されたビューの外部で開くファイルを信頼する際**に、ユーザーが安全に実行できるようにする] セクションの選択内容を確認します。

- Exchange Online PowerShell で次のコマンドを実行し、プロパティの値を確認します。

  ```powershell
  Get-AtpPolicyForO365 | Format-List *SafeDocs*
  ```
