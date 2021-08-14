---
title: Azure ゲートウェイ サブネットのアドレス空間計算
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 01/07/2021
audience: ITPro
ms.topic: hub-page
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
description: '概要: C3、Python、または PowerShell を使用して Azure ゲートウェイ サブネットのアドレス空間を計算します。'
ms.openlocfilehash: 7f5fce25a6d3725dbb80d3dcfe0a47153b2134e02d2db66b78252097e1009614
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53813248"
---
# <a name="address-space-calculator-for-azure-gateway-subnets"></a>Azure ゲートウェイ サブネットのアドレス空間計算

他のネットワークに接続されている Azure インフラストラクチャ サービスの仮想ネットワーク (VNet) には、ゲートウェイ サブネットが必要です。 ゲートウェイ サブネットを定義するためのベスト プラクティスは次のとおりです。

- ゲートウェイ サブネットのプレフィックスの長さは最大で 29 (10.119.255.248/29 など) ですが、現在の推奨事項は、プレフィックスの長さが 27 (10.119.255.224/27 など) を使用する方法です。
- ゲートウェイ サブネットのアドレス空間を定義する場合は、VNet アドレス空間の最後の部分を使用します。

2 番目の推奨事項では、ゲートウェイ サブネットに使用するビットを 0 に設定し、VNet アドレス空間の残りのビットを 1 に設定して、ゲートウェイ サブネットのアドレス空間を決定できます。 バイナリに変換して 10 進数に戻さずにゲートウェイ サブネット アドレス空間をすばやく計算するには、C# または Python または PowerShell コマンド ブロックで記述されたコンソール アプリケーションを使用できます。

この記事では、vNet アドレス プレフィックスの w.x.y.z/n の値とゲートウェイ サブネット プレフィックスの長さに基づいてゲートウェイ サブネット アドレス空間を計算する C#、Python、および PowerShell のコード ブロックについて説明します。

## <a name="c-code-block"></a>C# コード ブロック

このコード ブロックを使用して、コンソール アプリを作成C#。

```c#
using System; 
using System.Collections.Generic; 
using System.Linq; 
using System.Text; 
using System.Threading.Tasks; 
 
namespace ConsoleApplication1 
{ 
    class Program 
    { 
        static void Main(string[] args) 
        { 
            // Declare variables. 
            const long wOctet = 16777216;  
            const long xOctet = 65536; 
            const long yOctet = 256; 
            double D; 
            int w, x, y, z, vnetPrefLen, gwPrefLen; 
            long d, w2, x2, y2, z2; 
             
 
            // Get the five values needed from the keyboard. 
            Console.WriteLine("**************************************************************************"); 
            Console.WriteLine("*** Gateway subnet address space calculator for Azure virtual networks ***");             
            Console.WriteLine("**************************************************************************");  
            Console.WriteLine(); 
            Console.WriteLine("Please supply your virtual network address space in the form of w.x.y.z/n."); 
            Console.WriteLine(); 
            Console.WriteLine("w="); 
            w = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("x="); 
            x = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("y="); 
            y = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("z="); 
            z = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine("n="); 
            vnetPrefLen = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine(); 
            Console.WriteLine("Now supply the prefix length of your gateway subnet:"); 
            gwPrefLen = Convert.ToInt32(Console.ReadLine()); 
            Console.WriteLine(); 
 
            // Perform the calculation. 
            D = w * wOctet + x * xOctet + y * yOctet + z; 
            for (int i = vnetPrefLen + 1; i < gwPrefLen + 1; i++) 
            { 
                D = D + Math.Pow(2, 32 - i); 
            } 
            d = Convert.ToInt64(D); 
            w2 = d / wOctet; 
            x2 = (d - w2 * wOctet) / xOctet;  
            y2 = (d - w2 * wOctet - x2 * xOctet) / yOctet; 
            z2 = d - w2 * wOctet - x2 * xOctet - y2 * yOctet; 
             
            // Display the result.             
            Console.WriteLine("**************************************************************************");  
            Console.WriteLine("For the Azure virtual address space {0}.{1}.{2}.{3}/{4}", w, x, y, z, vnetPrefLen); 
            Console.WriteLine("and gateway prefix length of {0}, the gateway subnet address space is:", gwPrefLen); 
            Console.WriteLine(); 
            Console.WriteLine("{0}.{1}.{2}.{3}/{4}", w2, x2, y2, z2, gwPrefLen); 
            Console.WriteLine(); 
            Console.WriteLine("Press ENTER to quit."); 
            Console.ReadLine(); 
        } 
    } 
} 
```

## <a name="python-code-block"></a>Python コード ブロック

Python でコンソール アプリを作成するには、このコード ブロックを使用します。

```python
import math 
# Collect the values of w.x.y.z/n for your VNet address space and g, the prefix length of your gateway subnet 
print("**************************************************************************")  
print("*** Gateway subnet address space calculator for Azure virtual networks ***")  
print("**************************************************************************\n")   
print("Please supply your virtual network address space in the form of w.x.y.z/n.");  
w=int(input("w = ")) 
x=int(input("x = ")) 
y=int(input("y = ")) 
z=int(input("z = ")) 
n=int(input("n = ")) 
print("")  
g=int(input("Now supply the prefix length of your gateway subnet: ")) 
print("")  
 
# Calculate  
wOctet = 16777216  
xOctet = 65536  
yOctet = 256  
D = w * wOctet + x * xOctet + y * yOctet + z 
for index in range(n + 1,g + 1): 
    D += 2**(32 - index)  
 
w2 = math.floor(D / wOctet)  
x2 = math.floor((D - w2 * wOctet) / xOctet) 
y2 = math.floor((D - w2 * wOctet - x2 * xOctet) / yOctet) 
z2 = D - w2 * wOctet - x2 * xOctet - y2 * yOctet  
 
# Display the result  
gwAddrPref= "Your gateway address prefix is: " + str(w2) + "." + str(x2) + "." + str(y2) + "." + str(z2) + "/" + str(g)  
print(gwAddrPref) 
```


## <a name="powershell-command-block"></a>PowerShell コマンド ブロック

値を入力し、PowerShell ウィンドウまたは PowerShell 統合スクリプト環境 (ISE) で結果のコマンド ブロックを実行します。

```powershell
# Specify the values of w.x.y.z/n for your VNet address space and g, the prefix length of your gateway subnet: 
$w= 
$x= 
$y= 
$z= 
$n= 
$g= 
# Calculate 
$wOctet = 16777216 
$xOctet = 65536 
$yOctet = 256 
[long]$D = $w * $wOctet + $x * $xOctet + $y * $yOctet + $z; 
for ($i = $n + 1; $i -lt $g + 1; $i++) 
{ 
$D = $D + [math]::pow(2, 32 - $i) 
} 
$w2 = [math]::floor($D / $wOctet) 
$x2 = [math]::floor( ($D - $w2 * $wOctet) / $xOctet ) 
$y2 = [math]::floor( ($D - $w2 * $wOctet - $x2 * $xOctet) / $yOctet ) 
$z2 = $D - $w2 * $wOctet - $x2 * $xOctet - $y2 * $yOctet 
# Display the result 
$dx= [string]$w2 + "." + [string]$x2 + "." + [string]$y2 + "." + [string]$z2 + "/" + [string]$g 
Write-Host "Your gateway address prefix is: " $dx
```
    
## <a name="related-topics"></a>関連トピック

[PowerShell で Microsoft 365を管理する](manage-microsoft-365-with-microsoft-365-powershell.md)